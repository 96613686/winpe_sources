# _DataCollector<IConfigurationDataCollector>::CreateOutputLocation(short,ushort * *)

- ea: `0x180059a40`
- end: `0x18005aa2f`
- name: `?CreateOutputLocation@?$_DataCollector@UIConfigurationDataCollector@@@@UEAAJFPEAPEAG@Z`
- size: `4079`
- prototype: `__int64 __fastcall(__int64, __int16, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

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
- `0x180059a40`
- `0x18006b12c`
- `0x180072200`
- `0x1800f9c48`
- `0x180116404`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a09e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a09e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a9d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a9d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059b2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059b2b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18005a090`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18005a090`

## string_xrefs

- `0x180059ae5`: `_DataCollector<struct IConfigurationDataCollector>::CreateOutputLocation`
- `0x180059bc7`: `_DataCollector<struct IConfigurationDataCollector>::CreateOutputLocation`
- `0x18005a971`: `_DataCollector<struct IConfigurationDataCollector>::CreateOutputLocation`

## pseudocode

```c
__int64 __fastcall _DataCollector<IConfigurationDataCollector>::CreateOutputLocation(
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
      "_DataCollector<struct IConfigurationDataCollector>::CreateOutputLocation",
      73,
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
      "_DataCollector<struct IConfigurationDataCollector>::CreateOutputLocation",
      73);
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
      "_DataCollector<struct IConfigurationDataCollector>::CreateOutputLocation",
      73);
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
0x180059a40  mov     [rsp-8+arg_8], rbx
0x180059a45  push    rbp
0x180059a46  push    rsi
0x180059a47  push    rdi
0x180059a48  push    r12
0x180059a4a  push    r13
0x180059a4c  push    r14
0x180059a4e  push    r15
0x180059a50  lea     rbp, [rsp-0C30h]
0x180059a58  sub     rsp, 0D30h
0x180059a5f  mov     rax, cs:__security_cookie
0x180059a66  xor     rax, rsp
0x180059a69  mov     [rbp+0C60h+var_40], rax
0x180059a70  xor     r14d, r14d
0x180059a73  mov     [rsp+0D60h+var_CE8], rcx
0x180059a78  xor     eax, eax
0x180059a7a  mov     [rbp+0C60h+var_CE0], r14d
0x180059a7e  cmp     dword ptr cs:xmmword_180169738, r14d
0x180059a85  xorps   xmm0, xmm0
0x180059a88  mov     qword ptr [rbp+0C60h+var_CD8+10h], rax
0x180059a8c  mov     rsi, r8
0x180059a8f  mov     eax, [rcx+38h]
0x180059a92  movzx   edi, dx
0x180059a95  mov     [rsp+0D60h+var_CF0], eax
0x180059a99  mov     r12, rcx
0x180059a9c  mov     [rbp+0C60h+nSize], r14d
0x180059aa0  mov     r13d, r14d
0x180059aa3  mov     r15d, r14d
0x180059aa6  movups  xmmword ptr [rbp+0C60h+var_CD8], xmm0
0x180059aaa  jz      short loc_180059B1F
0x180059aac  mov     rdx, 4000000000000400h
0x180059ab6  test    qword ptr cs:xmmword_180169738+8, rdx
0x180059abd  jz      short loc_180059B1F
0x180059abf  mov     rax, cs:qword_180169748
0x180059ac6  and     rax, rdx
0x180059ac9  cmp     cs:qword_180169748, rax
0x180059ad0  jnz     short loc_180059B1F
0x180059ad2  mov     [rsp+0D60h+var_D20], 4
0x180059adb  lea     rax, [rsp+0D60h+var_CF0]
0x180059ae0  mov     [rsp+0D60h+var_D28], rax
0x180059ae5  lea     r9, aDatacollectorS_107; "_DataCollector<struct IConfigurationDat"...
0x180059aec  lea     rax, [rsp+0D60h+var_CE8]
0x180059af1  mov     [rsp+0D60h+var_D30], 8
0x180059afa  mov     [rsp+0D60h+var_D38], rax
0x180059aff  lea     r8d, [r14+3]
0x180059b03  lea     rdx, PLA_EVENT_METHOD
0x180059b0a  mov     qword ptr [rsp+0D60h+var_D40], 49h ; 'I'; int
0x180059b13  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180059b1a  call    EventingWriteEvent
0x180059b1f  cmp     [r12+8], r14d
0x180059b24  jz      short loc_180059B31
0x180059b26  lea     rcx, [r12+10h]; lpCriticalSection
0x180059b2b  call    cs:__imp_EnterCriticalSection
0x180059b31  lea     rcx, [rbp+0C60h+var_CD8]; struct tagVARIANT *
0x180059b35  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x180059b3a  test    rsi, rsi
0x180059b3d  jnz     loc_180059BE6
0x180059b43  xor     edi, edi
0x180059b45  mov     ebx, 80004003h
0x180059b4a  cmp     dword ptr cs:xmmword_180169738, edi
0x180059b50  mov     [rsp+0D60h+var_CF0], edi
0x180059b54  mov     dword ptr [rsp+0D60h+var_CE8], ebx
0x180059b58  jz      loc_18005A9C4
0x180059b5e  mov     rdx, 4000000000000800h; unsigned __int64
0x180059b68  test    qword ptr cs:xmmword_180169738+8, rdx
0x180059b6f  jz      loc_18005A9C4
0x180059b75  mov     rax, cs:qword_180169748
0x180059b7c  and     rax, rdx
0x180059b7f  cmp     cs:qword_180169748, rax
0x180059b86  jnz     loc_18005A9C4
0x180059b8c  lea     rcx, [rbp+0C60h+var_CC0]; unsigned __int16 *
0x180059b90  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180059b95  lea     rcx, [rbp+0C60h+var_CC0]
0x180059b99  or      rax, 0FFFFFFFFFFFFFFFFh
0x180059b9d  inc     rax
0x180059ba0  cmp     [rcx+rax*2], di
0x180059ba4  jnz     short loc_180059B9D
0x180059ba6  lea     ecx, [rax+rax]
0x180059ba9  lea     rax, [rbp+0C60h+var_CC0]
0x180059bad  add     rcx, 2
0x180059bb1  mov     [rsp+0D60h+var_D00], rcx
0x180059bb6  lea     r14, qword_180147320
0x180059bbd  mov     [rsp+0D60h+var_D08], rax
0x180059bc2  lea     r9, [rsp+0D60h+var_CE8]
0x180059bc7  lea     rax, aDatacollectorS_107; "_DataCollector<struct IConfigurationDat"...
0x180059bce  mov     [rsp+0D60h+var_D10], 49h ; 'I'
0x180059bd7  mov     [rsp+0D60h+var_D18], rax
0x180059bdc  lea     rax, [rsp+0D60h+var_CF0]
0x180059be1  jmp     loc_18005A98B
0x180059be6  mov     rcx, [r12+48h]
0x180059beb  test    rcx, rcx
0x180059bee  jnz     short loc_180059C66
0x180059bf0  xor     edi, edi
0x180059bf2  mov     ebx, 80300002h
0x180059bf7  cmp     dword ptr cs:xmmword_180169738, edi
0x180059bfd  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x180059c01  mov     [rsp+0D60h+var_CF0], ebx
0x180059c05  jz      loc_18005A9C4
0x180059c0b  mov     rdx, 4000000000000800h; unsigned __int64
0x180059c15  test    qword ptr cs:xmmword_180169738+8, rdx
0x180059c1c  jz      loc_18005A9C4
0x180059c22  mov     rax, cs:qword_180169748
0x180059c29  and     rax, rdx
0x180059c2c  cmp     cs:qword_180169748, rax
0x180059c33  jnz     loc_18005A9C4
0x180059c39  lea     rcx, [rbp+0C60h+var_C40]; unsigned __int16 *
0x180059c3d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180059c42  lea     rcx, [rbp+0C60h+var_C40]
0x180059c46  or      rax, 0FFFFFFFFFFFFFFFFh
0x180059c4a  inc     rax
0x180059c4d  cmp     [rcx+rax*2], di
0x180059c51  jnz     short loc_180059C4A
0x180059c53  lea     ecx, [rax+rax]
0x180059c56  lea     rax, [rbp+0C60h+var_C40]
0x180059c5a  lea     r14, qword_180147320
0x180059c61  jmp     loc_18005A95E
0x180059c66  mov     rax, [rcx]
0x180059c69  lea     rdx, [rbp+0C60h+var_CE0]
0x180059c6d  mov     rax, [rax+0F0h]
0x180059c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c79  mov     ebx, eax
0x180059c7b  test    eax, eax
0x180059c7d  jns     short loc_180059CF2
0x180059c7f  xor     edi, edi
0x180059c81  mov     [rsp+0D60h+var_CF0], eax
0x180059c85  cmp     dword ptr cs:xmmword_180169738, edi
0x180059c8b  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x180059c8f  jz      loc_18005A9C4
0x180059c95  mov     rdx, 4000000000000800h; unsigned __int64
0x180059c9f  test    qword ptr cs:xmmword_180169738+8, rdx
0x180059ca6  jz      loc_18005A9C4
0x180059cac  mov     rax, cs:qword_180169748
0x180059cb3  and     rax, rdx
0x180059cb6  cmp     cs:qword_180169748, rax
0x180059cbd  jnz     loc_18005A9C4
0x180059cc3  lea     rcx, [rbp+0C60h+var_BC0]; unsigned __int16 *
0x180059cca  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180059ccf  lea     rcx, [rbp+0C60h+var_BC0]
0x180059cd6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180059cda  inc     rax
0x180059cdd  cmp     [rcx+rax*2], di
0x180059ce1  jnz     short loc_180059CDA
0x180059ce3  lea     ecx, [rax+rax]
0x180059ce6  lea     rax, [rbp+0C60h+var_BC0]
0x180059ced  jmp     loc_180059C5A
0x180059cf2  xor     r8d, r8d; int
0x180059cf5  lea     r14, qword_180147320
0x180059cfc  mov     r9, r14; char *
0x180059cff  mov     ecx, 800h; dwBytes
0x180059d04  lea     edx, [r8+1]; int
0x180059d08  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x180059d0d  xor     ebx, ebx
0x180059d0f  mov     r13, rax
0x180059d12  test    rax, rax
0x180059d15  jnz     short loc_180059D91
0x180059d17  xor     edi, edi
0x180059d19  mov     ecx, 8007000Eh
0x180059d1e  cmp     dword ptr cs:xmmword_180169738, edi
0x180059d24  mov     ebx, ecx
0x180059d26  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x180059d2a  mov     [rsp+0D60h+var_CF0], ecx
0x180059d2e  jz      loc_18005A9C4
0x180059d34  mov     rdx, 4000000000000800h; unsigned __int64
0x180059d3e  test    qword ptr cs:xmmword_180169738+8, rdx
0x180059d45  jz      loc_18005A9C4
0x180059d4b  mov     rax, cs:qword_180169748
0x180059d52  and     rax, rdx
0x180059d55  cmp     cs:qword_180169748, rax
0x180059d5c  jnz     loc_18005A9C4
0x180059d62  lea     rcx, [rbp+0C60h+var_B40]; unsigned __int16 *
0x180059d69  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180059d6e  lea     rcx, [rbp+0C60h+var_B40]
0x180059d75  or      rax, 0FFFFFFFFFFFFFFFFh
0x180059d79  inc     rax
0x180059d7c  cmp     [rcx+rax*2], di
0x180059d80  jnz     short loc_180059D79
0x180059d82  lea     ecx, [rax+rax]
0x180059d85  lea     rax, [rbp+0C60h+var_B40]
0x180059d8c  jmp     loc_18005A95E
0x180059d91  xor     r8d, r8d; int
0x180059d94  mov     r9, r14; char *
0x180059d97  mov     ecx, 800h; dwBytes
0x180059d9c  lea     edx, [r8+1]; int
0x180059da0  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x180059da5  mov     r15, rax
0x180059da8  test    rax, rax
0x180059dab  jnz     short loc_180059E27
0x180059dad  xor     edi, edi
0x180059daf  mov     ecx, 8007000Eh
0x180059db4  cmp     dword ptr cs:xmmword_180169738, edi
0x180059dba  mov     ebx, ecx
0x180059dbc  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x180059dc0  mov     [rsp+0D60h+var_CF0], ecx
0x180059dc4  jz      loc_18005A9C4
0x180059dca  mov     rdx, 4000000000000800h; unsigned __int64
0x180059dd4  test    qword ptr cs:xmmword_180169738+8, rdx
0x180059ddb  jz      loc_18005A9C4
0x180059de1  mov     rax, cs:qword_180169748
0x180059de8  and     rax, rdx
0x180059deb  cmp     cs:qword_180169748, rax
0x180059df2  jnz     loc_18005A9C4
0x180059df8  lea     rcx, [rbp+0C60h+var_AC0]; unsigned __int16 *
0x180059dff  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180059e04  lea     rcx, [rbp+0C60h+var_AC0]
0x180059e0b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180059e0f  inc     rax
0x180059e12  cmp     [rcx+rax*2], di
0x180059e16  jnz     short loc_180059E0F
0x180059e18  lea     ecx, [rax+rax]
0x180059e1b  lea     rax, [rbp+0C60h+var_AC0]
0x180059e22  jmp     loc_18005A95E
0x180059e27  lea     rcx, [rbp+0C60h+var_CD8]; struct tagVARIANT *
0x180059e2b  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x180059e30  mov     rcx, [r12+48h]
0x180059e35  lea     rdx, [rbp+0C60h+var_CD8+8]
0x180059e39  mov     rax, [rcx]
0x180059e3c  cmp     bx, di
0x180059e3f  jz      loc_180059ECE
0x180059e45  mov     rax, [rax+90h]
0x180059e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e51  xor     edi, edi
0x180059e53  mov     ebx, eax
0x180059e55  test    eax, eax
0x180059e57  jns     loc_180059F53
0x180059e5d  cmp     dword ptr cs:xmmword_180169738, edi
0x180059e63  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x180059e67  mov     [rsp+0D60h+var_CF0], eax
0x180059e6b  jz      loc_18005A9C4
0x180059e71  mov     rdx, 4000000000000800h; unsigned __int64
0x180059e7b  test    qword ptr cs:xmmword_180169738+8, rdx
0x180059e82  jz      loc_18005A9C4
0x180059e88  mov     rax, cs:qword_180169748
0x180059e8f  and     rax, rdx
0x180059e92  cmp     cs:qword_180169748, rax
0x180059e99  jnz     loc_18005A9C4
0x180059e9f  lea     rcx, [rbp+0C60h+var_A40]; unsigned __int16 *
0x180059ea6  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180059eab  lea     rcx, [rbp+0C60h+var_A40]
0x180059eb2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180059eb6  inc     rax
0x180059eb9  cmp     [rcx+rax*2], di
0x180059ebd  jnz     short loc_180059EB6
0x180059ebf  lea     ecx, [rax+rax]
0x180059ec2  lea     rax, [rbp+0C60h+var_A40]
0x180059ec9  jmp     loc_18005A95E
0x180059ece  mov     rax, [rax+0A8h]
0x180059ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059eda  xor     edi, edi
0x180059edc  mov     ebx, eax
0x180059ede  test    eax, eax
0x180059ee0  jns     short loc_180059F53
0x180059ee2  cmp     dword ptr cs:xmmword_180169738, edi
0x180059ee8  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x180059eec  mov     [rsp+0D60h+var_CF0], eax
0x180059ef0  jz      loc_18005A9C4
0x180059ef6  mov     rdx, 4000000000000800h; unsigned __int64
0x180059f00  test    qword ptr cs:xmmword_180169738+8, rdx
0x180059f07  jz      loc_18005A9C4
0x180059f0d  mov     rax, cs:qword_180169748
0x180059f14  and     rax, rdx
0x180059f17  cmp     cs:qword_180169748, rax
0x180059f1e  jnz     loc_18005A9C4
0x180059f24  lea     rcx, [rbp+0C60h+var_9C0]; unsigned __int16 *
0x180059f2b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180059f30  lea     rcx, [rbp+0C60h+var_9C0]
0x180059f37  or      rax, 0FFFFFFFFFFFFFFFFh
0x180059f3b  inc     rax
0x180059f3e  cmp     [rcx+rax*2], di
0x180059f42  jnz     short loc_180059F3B
0x180059f44  lea     ecx, [rax+rax]
0x180059f47  lea     rax, [rbp+0C60h+var_9C0]
0x180059f4e  jmp     loc_18005A95E
0x180059f53  mov     r8, qword ptr [rbp+0C60h+var_CD8+8]; unsigned __int16 *
0x180059f57  mov     eax, 8
0x180059f5c  mov     word ptr [rbp+0C60h+var_CD8], ax
0x180059f60  test    r8, r8
0x180059f63  jz      loc_18005A8ED
0x180059f69  cmp     di, [r8]
0x180059f6d  jz      loc_18005A8ED
0x180059f73  mov     edx, 400h; unsigned __int64
0x180059f78  mov     rcx, r15; unsigned __int16 *
0x180059f7b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180059f80  mov     ebx, eax
0x180059f82  test    eax, eax
0x180059f84  jns     short loc_180059FF7
0x180059f86  cmp     dword ptr cs:xmmword_180169738, edi
0x180059f8c  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x180059f90  mov     [rsp+0D60h+var_CF0], eax
0x180059f94  jz      loc_18005A9C4
0x180059f9a  mov     rdx, 4000000000000800h; unsigned __int64
0x180059fa4  test    qword ptr cs:xmmword_180169738+8, rdx
0x180059fab  jz      loc_18005A9C4
0x180059fb1  mov     rax, cs:qword_180169748
0x180059fb8  and     rax, rdx
0x180059fbb  cmp     cs:qword_180169748, rax
0x180059fc2  jnz     loc_18005A9C4
0x180059fc8  lea     rcx, [rbp+0C60h+var_940]; unsigned __int16 *
0x180059fcf  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180059fd4  lea     rcx, [rbp+0C60h+var_940]
0x180059fdb  or      rax, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
