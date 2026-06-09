# _DataCollector<IApiTracingDataCollector>::CreateOutputLocation(short,ushort * *)

- ea: `0x1800ef310`
- end: `0x1800f02ff`
- name: `?CreateOutputLocation@?$_DataCollector@UIApiTracingDataCollector@@@@UEAAJFPEAPEAG@Z`
- size: `4079`
- prototype: ``
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
- `0x1800ef310`
- `0x1800f9c48`
- `0x180116404`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef96e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef96e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f02a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f02a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ef3fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ef3fb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800ef960`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800ef960`

## string_xrefs

- `0x1800ef3b5`: `_DataCollector<struct IApiTracingDataCollector>::CreateOutputLocation`
- `0x1800ef497`: `_DataCollector<struct IApiTracingDataCollector>::CreateOutputLocation`
- `0x1800f0241`: `_DataCollector<struct IApiTracingDataCollector>::CreateOutputLocation`

## pseudocode

```c
__int64 __fastcall _DataCollector<IApiTracingDataCollector>::CreateOutputLocation(
        __int64 a1,
        __int16 a2,
        unsigned __int16 **a3)
{
  WCHAR *v6; // r13
  unsigned __int16 *v7; // r15
  unsigned int v8; // ebx
  __int64 v9; // rax
  int *v10; // r9
  int *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 *v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  unsigned __int64 v25; // rdx
  const unsigned __int16 *v26; // r8
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  DWORD LastError; // eax
  int v31; // eax
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // rax
  int v37; // eax
  __int64 v38; // rax
  LONGLONG llVal; // r8
  int v40; // eax
  __int64 v41; // rax
  int v42; // eax
  unsigned __int64 v43; // rdx
  __int64 v44; // rax
  int v45; // eax
  __int64 v46; // rax
  int v47; // eax
  __int64 v48; // rax
  unsigned int v49; // ecx
  int appended; // eax
  __int64 v51; // rax
  int v52; // eax
  __int64 v53; // rax
  const unsigned __int16 *v54; // r8
  __int64 v55; // rax
  int v56; // eax
  unsigned __int64 v57; // rdx
  __int64 v58; // rax
  int v59; // eax
  __int64 v60; // rax
  int v61; // eax
  const char *v62; // rdx
  int v63; // r8d
  __int64 v64; // rax
  unsigned __int16 *v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  int v69; // [rsp+20h] [rbp-E0h]
  int v70; // [rsp+20h] [rbp-E0h]
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
      &PLA_EVENT_METHOD,
      3,
      "_DataCollector<struct IApiTracingDataCollector>::CreateOutputLocation",
      70,
      &v72,
      8,
      &v71,
      4);
  }
  if ( *(_DWORD *)(a1 + 8) )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  PlaiVariantInit(&v75);
  if ( a3 )
  {
    v12 = *(_QWORD *)(a1 + 72);
    if ( !v12 )
    {
      v8 = -2144337918;
      LODWORD(v72) = 0;
      v71 = -2144337918;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_193;
      }
      PlaiWhoAmI(v77, 0x4000000000000800uLL);
      v13 = -1;
      do
        ++v13;
      while ( v77[v13] );
      goto LABEL_191;
    }
    v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 240LL))(v12, &v73);
    v8 = v14;
    if ( v14 < 0 )
    {
      v71 = v14;
      LODWORD(v72) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_193;
      }
      PlaiWhoAmI(v78, 0x4000000000000800uLL);
      v15 = -1;
      do
        ++v15;
      while ( v78[v15] );
      goto LABEL_191;
    }
    v6 = (WCHAR *)PlaiAlloc(0x800u, 1, 0, byte_180147320, v69);
    if ( !v6 )
    {
      v8 = -2147024882;
      LODWORD(v72) = 0;
      v71 = -2147024882;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_193;
      }
      PlaiWhoAmI(v79, 0x4000000000000800uLL);
      v16 = -1;
      do
        ++v16;
      while ( v79[v16] );
      goto LABEL_191;
    }
    v7 = (unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, byte_180147320, v70);
    if ( !v7 )
    {
      v8 = -2147024882;
      LODWORD(v72) = 0;
      v71 = -2147024882;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_193;
      }
      PlaiWhoAmI(v80, 0x4000000000000800uLL);
      v17 = -1;
      do
        ++v17;
      while ( v80[v17] );
      goto LABEL_191;
    }
    PlaiVariantClear(&v75);
    v18 = *(__int64 **)(a1 + 72);
    v19 = *v18;
    if ( a2 )
    {
      v20 = (*(__int64 (__fastcall **)(__int64 *, CY *))(v19 + 144))(v18, &v75.cyVal);
      v8 = v20;
      if ( v20 < 0 )
      {
        LODWORD(v72) = 0;
        v71 = v20;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_193;
        }
        PlaiWhoAmI(v81, 0x4000000000000800uLL);
        v21 = -1;
        do
          ++v21;
        while ( v81[v21] );
        goto LABEL_191;
      }
    }
    else
    {
      v22 = (*(__int64 (__fastcall **)(__int64 *, CY *))(v19 + 168))(v18, &v75.cyVal);
      v8 = v22;
      if ( v22 < 0 )
      {
        LODWORD(v72) = 0;
        v71 = v22;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_193;
        }
        PlaiWhoAmI(v82, 0x4000000000000800uLL);
        v23 = -1;
        do
          ++v23;
        while ( v82[v23] );
        goto LABEL_191;
      }
    }
    v75.vt = 8;
    if ( v75.llVal && *v75.bstrVal )
    {
      v24 = StringCchCopyW(v7, 0x400u, v75.bstrVal);
      v8 = v24;
      if ( v24 < 0 )
      {
        LODWORD(v72) = 0;
        v71 = v24;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_193;
        }
        PlaiWhoAmI(v83, 0x4000000000000800uLL);
        v27 = -1;
        do
          ++v27;
        while ( v83[v27] );
        goto LABEL_191;
      }
      v28 = PlaiPathCat(v7, v25, v26);
      v8 = v28;
      if ( v28 < 0 )
      {
        LODWORD(v72) = 0;
        v71 = v28;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_193;
        }
        PlaiWhoAmI(v84, 0x4000000000000800uLL);
        v29 = -1;
        do
          ++v29;
        while ( v84[v29] );
        goto LABEL_191;
      }
      if ( (*(_BYTE *)(a1 + 88) & 2) != 0 )
      {
        nSize = 1024;
        if ( !GetComputerNameW(v6, &nSize) )
        {
          LastError = GetLastError();
          v31 = PlaiHResultFromWin32(LastError);
          v8 = v31;
          if ( v31 < 0 )
          {
            LODWORD(v72) = 0;
            v71 = v31;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_193;
            }
            PlaiWhoAmI(v85, 0x4000000000000800uLL);
            v32 = -1;
            do
              ++v32;
            while ( v85[v32] );
            goto LABEL_191;
          }
        }
        v33 = StringCchCatW(v7, 0x400u, v6);
        v8 = v33;
        if ( v33 < 0 )
        {
          LODWORD(v72) = 0;
          v71 = v33;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_193;
          }
          PlaiWhoAmI(v86, 0x4000000000000800uLL);
          v34 = -1;
          do
            ++v34;
          while ( v86[v34] );
          goto LABEL_191;
        }
        v35 = StringCchCatW(v7, 0x400u, L"_");
        v8 = v35;
        if ( v35 < 0 )
        {
          LODWORD(v72) = 0;
          v71 = v35;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_193;
          }
          PlaiWhoAmI(v87, 0x4000000000000800uLL);
          v36 = -1;
          do
            ++v36;
          while ( v87[v36] );
          goto LABEL_191;
        }
      }
      PlaiVariantClear(&v75);
      v37 = (*(__int64 (__fastcall **)(__int64, CY *))(*(_QWORD *)a1 + 80LL))(a1, &v75.cyVal);
      v8 = v37;
      if ( v37 < 0 )
      {
        LODWORD(v72) = 0;
        v71 = v37;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_193;
        }
        PlaiWhoAmI(v88, 0x4000000000000800uLL);
        v38 = -1;
        do
          ++v38;
        while ( v88[v38] );
        goto LABEL_191;
      }
      llVal = v75.llVal;
      v75.vt = 8;
      if ( v75.llVal )
      {
        if ( *v75.bstrVal )
        {
          v40 = StringCchCatW(v7, 0x400u, v75.bstrVal);
          v8 = v40;
          if ( v40 < 0 )
          {
            LODWORD(v72) = 0;
            v71 = v40;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_193;
            }
            PlaiWhoAmI(v89, 0x4000000000000800uLL);
            v41 = -1;
            do
              ++v41;
            while ( v89[v41] );
            goto LABEL_191;
          }
        }
      }
      if ( (*(_BYTE *)(a1 + 88) & 1) == 0 )
        goto LABEL_136;
      PlaiVariantClear(&v75);
      v42 = (*(__int64 (__fastcall **)(__int64, CY *))(*(_QWORD *)a1 + 112LL))(a1, &v75.cyVal);
      v8 = v42;
      if ( v42 < 0 )
      {
        LODWORD(v72) = 0;
        v71 = v42;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_193;
        }
        PlaiWhoAmI(v90, 0x4000000000000800uLL);
        v44 = -1;
        do
          ++v44;
        while ( v90[v44] );
        goto LABEL_191;
      }
      llVal = v75.llVal;
      v75.vt = 8;
      if ( !v75.llVal || !*v75.bstrVal )
        goto LABEL_136;
      v45 = PlaiExpandPattern(v6, v43, v75.bstrVal, v73);
      v8 = v45;
      if ( v45 < 0 )
      {
        LODWORD(v72) = 0;
        v71 = v45;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_193;
        }
        PlaiWhoAmI(v91, 0x4000000000000800uLL);
        v46 = -1;
        do
          ++v46;
        while ( v91[v46] );
        goto LABEL_191;
      }
      v47 = StringCchCatW(v7, 0x400u, v6);
      v8 = v47;
      if ( v47 < 0 )
      {
        LODWORD(v72) = 0;
        v71 = v47;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_193;
        }
        PlaiWhoAmI(v92, 0x4000000000000800uLL);
        v48 = -1;
        do
          ++v48;
        while ( v92[v48] );
      }
      else
      {
LABEL_136:
        v49 = *(_DWORD *)(a1 + 88);
        if ( (v49 & 0xFF00) != 0 && (appended = PlaiAppendAutoPattern(v49, v7, llVal, v73), v8 = appended, appended < 0) )
        {
          LODWORD(v72) = 0;
          v71 = appended;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_193;
          }
          PlaiWhoAmI(v93, 0x4000000000000800uLL);
          v51 = -1;
          do
            ++v51;
          while ( v93[v51] );
        }
        else
        {
          v52 = StringCchCatW(v7, 0x400u, L".");
          v8 = v52;
          if ( v52 >= 0 )
          {
            v54 = *(const unsigned __int16 **)(a1 + 144);
            if ( v54 )
            {
              v56 = StringCchCatW(v7, 0x400u, v54);
              v8 = v56;
              if ( v56 >= 0 )
              {
                v59 = PlaiExpandVariables(v7, v57, v7);
                v8 = v59;
                if ( v59 >= 0 )
                {
                  v61 = PlaiValidatePath(v7, 1u);
                  v8 = v61;
                  if ( v61 >= 0 )
                  {
                    v65 = PlaiAllocStringEx(v7, v62, v63);
                    *a3 = v65;
                    if ( v65 )
                      goto LABEL_193;
                    v8 = -2147024882;
                    v71 = -2147024882;
                    LODWORD(v72) = 0;
                    if ( !(_DWORD)xmmword_180169738
                      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                    {
                      goto LABEL_193;
                    }
                    PlaiWhoAmI(v99, 0x4000000000000800uLL);
                    v66 = -1;
                    do
                      ++v66;
                    while ( v99[v66] );
                  }
                  else
                  {
                    LODWORD(v72) = 0;
                    v71 = v61;
                    if ( !(_DWORD)xmmword_180169738
                      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                    {
                      goto LABEL_193;
                    }
                    PlaiWhoAmI(v98, 0x4000000000000800uLL);
                    v64 = -1;
                    do
                      ++v64;
                    while ( v98[v64] );
                  }
                }
                else
                {
                  LODWORD(v72) = 0;
                  v71 = v59;
                  if ( !(_DWORD)xmmword_180169738
                    || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                  {
                    goto LABEL_193;
                  }
                  PlaiWhoAmI(v97, 0x4000000000000800uLL);
                  v60 = -1;
                  do
                    ++v60;
                  while ( v97[v60] );
                }
              }
              else
              {
                LODWORD(v72) = 0;
                v71 = v56;
                if ( !(_DWORD)xmmword_180169738
                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                {
                  goto LABEL_193;
                }
                PlaiWhoAmI(v96, 0x4000000000000800uLL);
                v58 = -1;
                do
                  ++v58;
                while ( v96[v58] );
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
                goto LABEL_193;
              }
              PlaiWhoAmI(v95, 0x4000000000000800uLL);
              v55 = -1;
              do
                ++v55;
              while ( v95[v55] );
            }
          }
          else
          {
            LODWORD(v72) = 0;
            v71 = v52;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_193;
            }
            PlaiWhoAmI(v94, 0x4000000000000800uLL);
            v53 = -1;
            do
              ++v53;
            while ( v94[v53] );
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
        goto LABEL_193;
      }
      PlaiWhoAmI(v100, 0x4000000000000800uLL);
      v67 = -1;
      do
        ++v67;
      while ( v100[v67] );
    }
LABEL_191:
    v10 = &v71;
    v11 = (int *)&v72;
LABEL_192:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v10, 4, byte_180147320, 1, v11, 4);
    goto LABEL_193;
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
    v10 = (int *)&v72;
    v11 = &v71;
    goto LABEL_192;
  }
LABEL_193:
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
0x1800ef310  mov     [rsp-8+arg_8], rbx
0x1800ef315  push    rbp
0x1800ef316  push    rsi
0x1800ef317  push    rdi
0x1800ef318  push    r12
0x1800ef31a  push    r13
0x1800ef31c  push    r14
0x1800ef31e  push    r15
0x1800ef320  lea     rbp, [rsp-0C30h]
0x1800ef328  sub     rsp, 0D30h
0x1800ef32f  mov     rax, cs:__security_cookie
0x1800ef336  xor     rax, rsp
0x1800ef339  mov     [rbp+0C60h+var_40], rax
0x1800ef340  xor     r14d, r14d
0x1800ef343  mov     [rsp+0D60h+var_CE8], rcx
0x1800ef348  xor     eax, eax
0x1800ef34a  mov     [rbp+0C60h+var_CE0], r14d
0x1800ef34e  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800ef355  xorps   xmm0, xmm0
0x1800ef358  mov     qword ptr [rbp+0C60h+var_CD8+10h], rax
0x1800ef35c  mov     rsi, r8
0x1800ef35f  mov     eax, [rcx+38h]
0x1800ef362  movzx   edi, dx
0x1800ef365  mov     [rsp+0D60h+var_CF0], eax
0x1800ef369  mov     r12, rcx
0x1800ef36c  mov     [rbp+0C60h+nSize], r14d
0x1800ef370  mov     r13d, r14d
0x1800ef373  mov     r15d, r14d
0x1800ef376  movups  xmmword ptr [rbp+0C60h+var_CD8], xmm0
0x1800ef37a  jz      short loc_1800EF3EF
0x1800ef37c  mov     rdx, 4000000000000400h
0x1800ef386  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ef38d  jz      short loc_1800EF3EF
0x1800ef38f  mov     rax, cs:qword_180169748
0x1800ef396  and     rax, rdx
0x1800ef399  cmp     cs:qword_180169748, rax
0x1800ef3a0  jnz     short loc_1800EF3EF
0x1800ef3a2  mov     [rsp+0D60h+var_D20], 4
0x1800ef3ab  lea     rax, [rsp+0D60h+var_CF0]
0x1800ef3b0  mov     [rsp+0D60h+var_D28], rax
0x1800ef3b5  lea     r9, aDatacollectorS_33; "_DataCollector<struct IApiTracingDataCo"...
0x1800ef3bc  lea     rax, [rsp+0D60h+var_CE8]
0x1800ef3c1  mov     [rsp+0D60h+var_D30], 8
0x1800ef3ca  mov     [rsp+0D60h+var_D38], rax
0x1800ef3cf  lea     r8d, [r14+3]
0x1800ef3d3  lea     rdx, PLA_EVENT_METHOD
0x1800ef3da  mov     qword ptr [rsp+0D60h+var_D40], 46h ; 'F'; int
0x1800ef3e3  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800ef3ea  call    EventingWriteEvent
0x1800ef3ef  cmp     [r12+8], r14d
0x1800ef3f4  jz      short loc_1800EF401
0x1800ef3f6  lea     rcx, [r12+10h]; lpCriticalSection
0x1800ef3fb  call    cs:__imp_EnterCriticalSection
0x1800ef401  lea     rcx, [rbp+0C60h+var_CD8]; struct tagVARIANT *
0x1800ef405  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x1800ef40a  test    rsi, rsi
0x1800ef40d  jnz     loc_1800EF4B6
0x1800ef413  xor     edi, edi
0x1800ef415  mov     ebx, 80004003h
0x1800ef41a  cmp     dword ptr cs:xmmword_180169738, edi
0x1800ef420  mov     [rsp+0D60h+var_CF0], edi
0x1800ef424  mov     dword ptr [rsp+0D60h+var_CE8], ebx
0x1800ef428  jz      loc_1800F0294
0x1800ef42e  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ef438  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ef43f  jz      loc_1800F0294
0x1800ef445  mov     rax, cs:qword_180169748
0x1800ef44c  and     rax, rdx
0x1800ef44f  cmp     cs:qword_180169748, rax
0x1800ef456  jnz     loc_1800F0294
0x1800ef45c  lea     rcx, [rbp+0C60h+var_CC0]; unsigned __int16 *
0x1800ef460  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ef465  lea     rcx, [rbp+0C60h+var_CC0]
0x1800ef469  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ef46d  inc     rax
0x1800ef470  cmp     [rcx+rax*2], di
0x1800ef474  jnz     short loc_1800EF46D
0x1800ef476  lea     ecx, [rax+rax]
0x1800ef479  lea     rax, [rbp+0C60h+var_CC0]
0x1800ef47d  add     rcx, 2
0x1800ef481  mov     [rsp+0D60h+var_D00], rcx
0x1800ef486  lea     r14, byte_180147320
0x1800ef48d  mov     [rsp+0D60h+var_D08], rax
0x1800ef492  lea     r9, [rsp+0D60h+var_CE8]
0x1800ef497  lea     rax, aDatacollectorS_33; "_DataCollector<struct IApiTracingDataCo"...
0x1800ef49e  mov     [rsp+0D60h+var_D10], 46h ; 'F'
0x1800ef4a7  mov     [rsp+0D60h+var_D18], rax
0x1800ef4ac  lea     rax, [rsp+0D60h+var_CF0]
0x1800ef4b1  jmp     loc_1800F025B
0x1800ef4b6  mov     rcx, [r12+48h]
0x1800ef4bb  test    rcx, rcx
0x1800ef4be  jnz     short loc_1800EF536
0x1800ef4c0  xor     edi, edi
0x1800ef4c2  mov     ebx, 80300002h
0x1800ef4c7  cmp     dword ptr cs:xmmword_180169738, edi
0x1800ef4cd  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800ef4d1  mov     [rsp+0D60h+var_CF0], ebx
0x1800ef4d5  jz      loc_1800F0294
0x1800ef4db  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ef4e5  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ef4ec  jz      loc_1800F0294
0x1800ef4f2  mov     rax, cs:qword_180169748
0x1800ef4f9  and     rax, rdx
0x1800ef4fc  cmp     cs:qword_180169748, rax
0x1800ef503  jnz     loc_1800F0294
0x1800ef509  lea     rcx, [rbp+0C60h+var_C40]; unsigned __int16 *
0x1800ef50d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ef512  lea     rcx, [rbp+0C60h+var_C40]
0x1800ef516  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ef51a  inc     rax
0x1800ef51d  cmp     [rcx+rax*2], di
0x1800ef521  jnz     short loc_1800EF51A
0x1800ef523  lea     ecx, [rax+rax]
0x1800ef526  lea     rax, [rbp+0C60h+var_C40]
0x1800ef52a  lea     r14, byte_180147320
0x1800ef531  jmp     loc_1800F022E
0x1800ef536  mov     rax, [rcx]
0x1800ef539  lea     rdx, [rbp+0C60h+var_CE0]
0x1800ef53d  mov     rax, [rax+0F0h]
0x1800ef544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef549  mov     ebx, eax
0x1800ef54b  test    eax, eax
0x1800ef54d  jns     short loc_1800EF5C2
0x1800ef54f  xor     edi, edi
0x1800ef551  mov     [rsp+0D60h+var_CF0], eax
0x1800ef555  cmp     dword ptr cs:xmmword_180169738, edi
0x1800ef55b  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800ef55f  jz      loc_1800F0294
0x1800ef565  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ef56f  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ef576  jz      loc_1800F0294
0x1800ef57c  mov     rax, cs:qword_180169748
0x1800ef583  and     rax, rdx
0x1800ef586  cmp     cs:qword_180169748, rax
0x1800ef58d  jnz     loc_1800F0294
0x1800ef593  lea     rcx, [rbp+0C60h+var_BC0]; unsigned __int16 *
0x1800ef59a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ef59f  lea     rcx, [rbp+0C60h+var_BC0]
0x1800ef5a6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ef5aa  inc     rax
0x1800ef5ad  cmp     [rcx+rax*2], di
0x1800ef5b1  jnz     short loc_1800EF5AA
0x1800ef5b3  lea     ecx, [rax+rax]
0x1800ef5b6  lea     rax, [rbp+0C60h+var_BC0]
0x1800ef5bd  jmp     loc_1800EF52A
0x1800ef5c2  xor     r8d, r8d; int
0x1800ef5c5  lea     r14, byte_180147320
0x1800ef5cc  mov     r9, r14; char *
0x1800ef5cf  mov     ecx, 800h; dwBytes
0x1800ef5d4  lea     edx, [r8+1]; int
0x1800ef5d8  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800ef5dd  xor     ebx, ebx
0x1800ef5df  mov     r13, rax
0x1800ef5e2  test    rax, rax
0x1800ef5e5  jnz     short loc_1800EF661
0x1800ef5e7  xor     edi, edi
0x1800ef5e9  mov     ecx, 8007000Eh
0x1800ef5ee  cmp     dword ptr cs:xmmword_180169738, edi
0x1800ef5f4  mov     ebx, ecx
0x1800ef5f6  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800ef5fa  mov     [rsp+0D60h+var_CF0], ecx
0x1800ef5fe  jz      loc_1800F0294
0x1800ef604  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ef60e  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ef615  jz      loc_1800F0294
0x1800ef61b  mov     rax, cs:qword_180169748
0x1800ef622  and     rax, rdx
0x1800ef625  cmp     cs:qword_180169748, rax
0x1800ef62c  jnz     loc_1800F0294
0x1800ef632  lea     rcx, [rbp+0C60h+var_B40]; unsigned __int16 *
0x1800ef639  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ef63e  lea     rcx, [rbp+0C60h+var_B40]
0x1800ef645  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ef649  inc     rax
0x1800ef64c  cmp     [rcx+rax*2], di
0x1800ef650  jnz     short loc_1800EF649
0x1800ef652  lea     ecx, [rax+rax]
0x1800ef655  lea     rax, [rbp+0C60h+var_B40]
0x1800ef65c  jmp     loc_1800F022E
0x1800ef661  xor     r8d, r8d; int
0x1800ef664  mov     r9, r14; char *
0x1800ef667  mov     ecx, 800h; dwBytes
0x1800ef66c  lea     edx, [r8+1]; int
0x1800ef670  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800ef675  mov     r15, rax
0x1800ef678  test    rax, rax
0x1800ef67b  jnz     short loc_1800EF6F7
0x1800ef67d  xor     edi, edi
0x1800ef67f  mov     ecx, 8007000Eh
0x1800ef684  cmp     dword ptr cs:xmmword_180169738, edi
0x1800ef68a  mov     ebx, ecx
0x1800ef68c  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800ef690  mov     [rsp+0D60h+var_CF0], ecx
0x1800ef694  jz      loc_1800F0294
0x1800ef69a  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ef6a4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ef6ab  jz      loc_1800F0294
0x1800ef6b1  mov     rax, cs:qword_180169748
0x1800ef6b8  and     rax, rdx
0x1800ef6bb  cmp     cs:qword_180169748, rax
0x1800ef6c2  jnz     loc_1800F0294
0x1800ef6c8  lea     rcx, [rbp+0C60h+var_AC0]; unsigned __int16 *
0x1800ef6cf  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ef6d4  lea     rcx, [rbp+0C60h+var_AC0]
0x1800ef6db  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ef6df  inc     rax
0x1800ef6e2  cmp     [rcx+rax*2], di
0x1800ef6e6  jnz     short loc_1800EF6DF
0x1800ef6e8  lea     ecx, [rax+rax]
0x1800ef6eb  lea     rax, [rbp+0C60h+var_AC0]
0x1800ef6f2  jmp     loc_1800F022E
0x1800ef6f7  lea     rcx, [rbp+0C60h+var_CD8]; struct tagVARIANT *
0x1800ef6fb  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800ef700  mov     rcx, [r12+48h]
0x1800ef705  lea     rdx, [rbp+0C60h+var_CD8+8]
0x1800ef709  mov     rax, [rcx]
0x1800ef70c  cmp     bx, di
0x1800ef70f  jz      loc_1800EF79E
0x1800ef715  mov     rax, [rax+90h]
0x1800ef71c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef721  xor     edi, edi
0x1800ef723  mov     ebx, eax
0x1800ef725  test    eax, eax
0x1800ef727  jns     loc_1800EF823
0x1800ef72d  cmp     dword ptr cs:xmmword_180169738, edi
0x1800ef733  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800ef737  mov     [rsp+0D60h+var_CF0], eax
0x1800ef73b  jz      loc_1800F0294
0x1800ef741  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ef74b  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ef752  jz      loc_1800F0294
0x1800ef758  mov     rax, cs:qword_180169748
0x1800ef75f  and     rax, rdx
0x1800ef762  cmp     cs:qword_180169748, rax
0x1800ef769  jnz     loc_1800F0294
0x1800ef76f  lea     rcx, [rbp+0C60h+var_A40]; unsigned __int16 *
0x1800ef776  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ef77b  lea     rcx, [rbp+0C60h+var_A40]
0x1800ef782  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ef786  inc     rax
0x1800ef789  cmp     [rcx+rax*2], di
0x1800ef78d  jnz     short loc_1800EF786
0x1800ef78f  lea     ecx, [rax+rax]
0x1800ef792  lea     rax, [rbp+0C60h+var_A40]
0x1800ef799  jmp     loc_1800F022E
0x1800ef79e  mov     rax, [rax+0A8h]
0x1800ef7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef7aa  xor     edi, edi
0x1800ef7ac  mov     ebx, eax
0x1800ef7ae  test    eax, eax
0x1800ef7b0  jns     short loc_1800EF823
0x1800ef7b2  cmp     dword ptr cs:xmmword_180169738, edi
0x1800ef7b8  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800ef7bc  mov     [rsp+0D60h+var_CF0], eax
0x1800ef7c0  jz      loc_1800F0294
0x1800ef7c6  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ef7d0  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ef7d7  jz      loc_1800F0294
0x1800ef7dd  mov     rax, cs:qword_180169748
0x1800ef7e4  and     rax, rdx
0x1800ef7e7  cmp     cs:qword_180169748, rax
0x1800ef7ee  jnz     loc_1800F0294
0x1800ef7f4  lea     rcx, [rbp+0C60h+var_9C0]; unsigned __int16 *
0x1800ef7fb  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ef800  lea     rcx, [rbp+0C60h+var_9C0]
0x1800ef807  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ef80b  inc     rax
0x1800ef80e  cmp     [rcx+rax*2], di
0x1800ef812  jnz     short loc_1800EF80B
0x1800ef814  lea     ecx, [rax+rax]
0x1800ef817  lea     rax, [rbp+0C60h+var_9C0]
0x1800ef81e  jmp     loc_1800F022E
0x1800ef823  mov     r8, qword ptr [rbp+0C60h+var_CD8+8]; unsigned __int16 *
0x1800ef827  mov     eax, 8
0x1800ef82c  mov     word ptr [rbp+0C60h+var_CD8], ax
0x1800ef830  test    r8, r8
0x1800ef833  jz      loc_1800F01BD
0x1800ef839  cmp     di, [r8]
0x1800ef83d  jz      loc_1800F01BD
0x1800ef843  mov     edx, 400h; unsigned __int64
0x1800ef848  mov     rcx, r15; unsigned __int16 *
0x1800ef84b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ef850  mov     ebx, eax
0x1800ef852  test    eax, eax
0x1800ef854  jns     short loc_1800EF8C7
0x1800ef856  cmp     dword ptr cs:xmmword_180169738, edi
0x1800ef85c  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800ef860  mov     [rsp+0D60h+var_CF0], eax
0x1800ef864  jz      loc_1800F0294
0x1800ef86a  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ef874  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ef87b  jz      loc_1800F0294
0x1800ef881  mov     rax, cs:qword_180169748
0x1800ef888  and     rax, rdx
0x1800ef88b  cmp     cs:qword_180169748, rax
0x1800ef892  jnz     loc_1800F0294
0x1800ef898  lea     rcx, [rbp+0C60h+var_940]; unsigned __int16 *
0x1800ef89f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ef8a4  lea     rcx, [rbp+0C60h+var_940]
0x1800ef8ab  or      rax, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
