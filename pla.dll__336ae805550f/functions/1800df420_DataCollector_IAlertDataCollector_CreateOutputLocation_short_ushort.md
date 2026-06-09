# _DataCollector<IAlertDataCollector>::CreateOutputLocation(short,ushort * *)

- ea: `0x1800df420`
- end: `0x1800e040f`
- name: `?CreateOutputLocation@?$_DataCollector@UIAlertDataCollector@@@@UEAAJFPEAPEAG@Z`
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
- `0x1800df420`
- `0x1800f9c48`
- `0x180116404`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfa7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfa7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e03b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e03b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800df50b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800df50b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800dfa70`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800dfa70`

## string_xrefs

- `0x1800df4c5`: `_DataCollector<struct IAlertDataCollector>::CreateOutputLocation`
- `0x1800df5a7`: `_DataCollector<struct IAlertDataCollector>::CreateOutputLocation`
- `0x1800e0351`: `_DataCollector<struct IAlertDataCollector>::CreateOutputLocation`

## pseudocode

```c
__int64 __fastcall _DataCollector<IAlertDataCollector>::CreateOutputLocation(
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
      "_DataCollector<struct IAlertDataCollector>::CreateOutputLocation",
      65,
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
0x1800df420  mov     [rsp-8+arg_8], rbx
0x1800df425  push    rbp
0x1800df426  push    rsi
0x1800df427  push    rdi
0x1800df428  push    r12
0x1800df42a  push    r13
0x1800df42c  push    r14
0x1800df42e  push    r15
0x1800df430  lea     rbp, [rsp-0C30h]
0x1800df438  sub     rsp, 0D30h
0x1800df43f  mov     rax, cs:__security_cookie
0x1800df446  xor     rax, rsp
0x1800df449  mov     [rbp+0C60h+var_40], rax
0x1800df450  xor     r14d, r14d
0x1800df453  mov     [rsp+0D60h+var_CE8], rcx
0x1800df458  xor     eax, eax
0x1800df45a  mov     [rbp+0C60h+var_CE0], r14d
0x1800df45e  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800df465  xorps   xmm0, xmm0
0x1800df468  mov     qword ptr [rbp+0C60h+var_CD8+10h], rax
0x1800df46c  mov     rsi, r8
0x1800df46f  mov     eax, [rcx+38h]
0x1800df472  movzx   edi, dx
0x1800df475  mov     [rsp+0D60h+var_CF0], eax
0x1800df479  mov     r12, rcx
0x1800df47c  mov     [rbp+0C60h+nSize], r14d
0x1800df480  mov     r13d, r14d
0x1800df483  mov     r15d, r14d
0x1800df486  movups  xmmword ptr [rbp+0C60h+var_CD8], xmm0
0x1800df48a  jz      short loc_1800DF4FF
0x1800df48c  mov     rdx, 4000000000000400h
0x1800df496  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800df49d  jz      short loc_1800DF4FF
0x1800df49f  mov     rax, cs:qword_180169748
0x1800df4a6  and     rax, rdx
0x1800df4a9  cmp     cs:qword_180169748, rax
0x1800df4b0  jnz     short loc_1800DF4FF
0x1800df4b2  mov     [rsp+0D60h+var_D20], 4
0x1800df4bb  lea     rax, [rsp+0D60h+var_CF0]
0x1800df4c0  mov     [rsp+0D60h+var_D28], rax
0x1800df4c5  lea     r9, aDatacollectorS_66; "_DataCollector<struct IAlertDataCollect"...
0x1800df4cc  lea     rax, [rsp+0D60h+var_CE8]
0x1800df4d1  mov     [rsp+0D60h+var_D30], 8
0x1800df4da  mov     [rsp+0D60h+var_D38], rax
0x1800df4df  lea     r8d, [r14+3]
0x1800df4e3  lea     rdx, PLA_EVENT_METHOD
0x1800df4ea  mov     qword ptr [rsp+0D60h+var_D40], 41h ; 'A'; int
0x1800df4f3  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800df4fa  call    EventingWriteEvent
0x1800df4ff  cmp     [r12+8], r14d
0x1800df504  jz      short loc_1800DF511
0x1800df506  lea     rcx, [r12+10h]; lpCriticalSection
0x1800df50b  call    cs:__imp_EnterCriticalSection
0x1800df511  lea     rcx, [rbp+0C60h+var_CD8]; struct tagVARIANT *
0x1800df515  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x1800df51a  test    rsi, rsi
0x1800df51d  jnz     loc_1800DF5C6
0x1800df523  xor     edi, edi
0x1800df525  mov     ebx, 80004003h
0x1800df52a  cmp     dword ptr cs:xmmword_180169738, edi
0x1800df530  mov     [rsp+0D60h+var_CF0], edi
0x1800df534  mov     dword ptr [rsp+0D60h+var_CE8], ebx
0x1800df538  jz      loc_1800E03A4
0x1800df53e  mov     rdx, 4000000000000800h; unsigned __int64
0x1800df548  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800df54f  jz      loc_1800E03A4
0x1800df555  mov     rax, cs:qword_180169748
0x1800df55c  and     rax, rdx
0x1800df55f  cmp     cs:qword_180169748, rax
0x1800df566  jnz     loc_1800E03A4
0x1800df56c  lea     rcx, [rbp+0C60h+var_CC0]; unsigned __int16 *
0x1800df570  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800df575  lea     rcx, [rbp+0C60h+var_CC0]
0x1800df579  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800df57d  inc     rax
0x1800df580  cmp     [rcx+rax*2], di
0x1800df584  jnz     short loc_1800DF57D
0x1800df586  lea     ecx, [rax+rax]
0x1800df589  lea     rax, [rbp+0C60h+var_CC0]
0x1800df58d  add     rcx, 2
0x1800df591  mov     [rsp+0D60h+var_D00], rcx
0x1800df596  lea     r14, byte_180147320
0x1800df59d  mov     [rsp+0D60h+var_D08], rax
0x1800df5a2  lea     r9, [rsp+0D60h+var_CE8]
0x1800df5a7  lea     rax, aDatacollectorS_66; "_DataCollector<struct IAlertDataCollect"...
0x1800df5ae  mov     [rsp+0D60h+var_D10], 41h ; 'A'
0x1800df5b7  mov     [rsp+0D60h+var_D18], rax
0x1800df5bc  lea     rax, [rsp+0D60h+var_CF0]
0x1800df5c1  jmp     loc_1800E036B
0x1800df5c6  mov     rcx, [r12+48h]
0x1800df5cb  test    rcx, rcx
0x1800df5ce  jnz     short loc_1800DF646
0x1800df5d0  xor     edi, edi
0x1800df5d2  mov     ebx, 80300002h
0x1800df5d7  cmp     dword ptr cs:xmmword_180169738, edi
0x1800df5dd  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800df5e1  mov     [rsp+0D60h+var_CF0], ebx
0x1800df5e5  jz      loc_1800E03A4
0x1800df5eb  mov     rdx, 4000000000000800h; unsigned __int64
0x1800df5f5  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800df5fc  jz      loc_1800E03A4
0x1800df602  mov     rax, cs:qword_180169748
0x1800df609  and     rax, rdx
0x1800df60c  cmp     cs:qword_180169748, rax
0x1800df613  jnz     loc_1800E03A4
0x1800df619  lea     rcx, [rbp+0C60h+var_C40]; unsigned __int16 *
0x1800df61d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800df622  lea     rcx, [rbp+0C60h+var_C40]
0x1800df626  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800df62a  inc     rax
0x1800df62d  cmp     [rcx+rax*2], di
0x1800df631  jnz     short loc_1800DF62A
0x1800df633  lea     ecx, [rax+rax]
0x1800df636  lea     rax, [rbp+0C60h+var_C40]
0x1800df63a  lea     r14, byte_180147320
0x1800df641  jmp     loc_1800E033E
0x1800df646  mov     rax, [rcx]
0x1800df649  lea     rdx, [rbp+0C60h+var_CE0]
0x1800df64d  mov     rax, [rax+0F0h]
0x1800df654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df659  mov     ebx, eax
0x1800df65b  test    eax, eax
0x1800df65d  jns     short loc_1800DF6D2
0x1800df65f  xor     edi, edi
0x1800df661  mov     [rsp+0D60h+var_CF0], eax
0x1800df665  cmp     dword ptr cs:xmmword_180169738, edi
0x1800df66b  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800df66f  jz      loc_1800E03A4
0x1800df675  mov     rdx, 4000000000000800h; unsigned __int64
0x1800df67f  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800df686  jz      loc_1800E03A4
0x1800df68c  mov     rax, cs:qword_180169748
0x1800df693  and     rax, rdx
0x1800df696  cmp     cs:qword_180169748, rax
0x1800df69d  jnz     loc_1800E03A4
0x1800df6a3  lea     rcx, [rbp+0C60h+var_BC0]; unsigned __int16 *
0x1800df6aa  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800df6af  lea     rcx, [rbp+0C60h+var_BC0]
0x1800df6b6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800df6ba  inc     rax
0x1800df6bd  cmp     [rcx+rax*2], di
0x1800df6c1  jnz     short loc_1800DF6BA
0x1800df6c3  lea     ecx, [rax+rax]
0x1800df6c6  lea     rax, [rbp+0C60h+var_BC0]
0x1800df6cd  jmp     loc_1800DF63A
0x1800df6d2  xor     r8d, r8d; int
0x1800df6d5  lea     r14, byte_180147320
0x1800df6dc  mov     r9, r14; char *
0x1800df6df  mov     ecx, 800h; dwBytes
0x1800df6e4  lea     edx, [r8+1]; int
0x1800df6e8  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800df6ed  xor     ebx, ebx
0x1800df6ef  mov     r13, rax
0x1800df6f2  test    rax, rax
0x1800df6f5  jnz     short loc_1800DF771
0x1800df6f7  xor     edi, edi
0x1800df6f9  mov     ecx, 8007000Eh
0x1800df6fe  cmp     dword ptr cs:xmmword_180169738, edi
0x1800df704  mov     ebx, ecx
0x1800df706  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800df70a  mov     [rsp+0D60h+var_CF0], ecx
0x1800df70e  jz      loc_1800E03A4
0x1800df714  mov     rdx, 4000000000000800h; unsigned __int64
0x1800df71e  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800df725  jz      loc_1800E03A4
0x1800df72b  mov     rax, cs:qword_180169748
0x1800df732  and     rax, rdx
0x1800df735  cmp     cs:qword_180169748, rax
0x1800df73c  jnz     loc_1800E03A4
0x1800df742  lea     rcx, [rbp+0C60h+var_B40]; unsigned __int16 *
0x1800df749  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800df74e  lea     rcx, [rbp+0C60h+var_B40]
0x1800df755  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800df759  inc     rax
0x1800df75c  cmp     [rcx+rax*2], di
0x1800df760  jnz     short loc_1800DF759
0x1800df762  lea     ecx, [rax+rax]
0x1800df765  lea     rax, [rbp+0C60h+var_B40]
0x1800df76c  jmp     loc_1800E033E
0x1800df771  xor     r8d, r8d; int
0x1800df774  mov     r9, r14; char *
0x1800df777  mov     ecx, 800h; dwBytes
0x1800df77c  lea     edx, [r8+1]; int
0x1800df780  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800df785  mov     r15, rax
0x1800df788  test    rax, rax
0x1800df78b  jnz     short loc_1800DF807
0x1800df78d  xor     edi, edi
0x1800df78f  mov     ecx, 8007000Eh
0x1800df794  cmp     dword ptr cs:xmmword_180169738, edi
0x1800df79a  mov     ebx, ecx
0x1800df79c  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800df7a0  mov     [rsp+0D60h+var_CF0], ecx
0x1800df7a4  jz      loc_1800E03A4
0x1800df7aa  mov     rdx, 4000000000000800h; unsigned __int64
0x1800df7b4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800df7bb  jz      loc_1800E03A4
0x1800df7c1  mov     rax, cs:qword_180169748
0x1800df7c8  and     rax, rdx
0x1800df7cb  cmp     cs:qword_180169748, rax
0x1800df7d2  jnz     loc_1800E03A4
0x1800df7d8  lea     rcx, [rbp+0C60h+var_AC0]; unsigned __int16 *
0x1800df7df  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800df7e4  lea     rcx, [rbp+0C60h+var_AC0]
0x1800df7eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800df7ef  inc     rax
0x1800df7f2  cmp     [rcx+rax*2], di
0x1800df7f6  jnz     short loc_1800DF7EF
0x1800df7f8  lea     ecx, [rax+rax]
0x1800df7fb  lea     rax, [rbp+0C60h+var_AC0]
0x1800df802  jmp     loc_1800E033E
0x1800df807  lea     rcx, [rbp+0C60h+var_CD8]; struct tagVARIANT *
0x1800df80b  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800df810  mov     rcx, [r12+48h]
0x1800df815  lea     rdx, [rbp+0C60h+var_CD8+8]
0x1800df819  mov     rax, [rcx]
0x1800df81c  cmp     bx, di
0x1800df81f  jz      loc_1800DF8AE
0x1800df825  mov     rax, [rax+90h]
0x1800df82c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df831  xor     edi, edi
0x1800df833  mov     ebx, eax
0x1800df835  test    eax, eax
0x1800df837  jns     loc_1800DF933
0x1800df83d  cmp     dword ptr cs:xmmword_180169738, edi
0x1800df843  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800df847  mov     [rsp+0D60h+var_CF0], eax
0x1800df84b  jz      loc_1800E03A4
0x1800df851  mov     rdx, 4000000000000800h; unsigned __int64
0x1800df85b  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800df862  jz      loc_1800E03A4
0x1800df868  mov     rax, cs:qword_180169748
0x1800df86f  and     rax, rdx
0x1800df872  cmp     cs:qword_180169748, rax
0x1800df879  jnz     loc_1800E03A4
0x1800df87f  lea     rcx, [rbp+0C60h+var_A40]; unsigned __int16 *
0x1800df886  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800df88b  lea     rcx, [rbp+0C60h+var_A40]
0x1800df892  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800df896  inc     rax
0x1800df899  cmp     [rcx+rax*2], di
0x1800df89d  jnz     short loc_1800DF896
0x1800df89f  lea     ecx, [rax+rax]
0x1800df8a2  lea     rax, [rbp+0C60h+var_A40]
0x1800df8a9  jmp     loc_1800E033E
0x1800df8ae  mov     rax, [rax+0A8h]
0x1800df8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df8ba  xor     edi, edi
0x1800df8bc  mov     ebx, eax
0x1800df8be  test    eax, eax
0x1800df8c0  jns     short loc_1800DF933
0x1800df8c2  cmp     dword ptr cs:xmmword_180169738, edi
0x1800df8c8  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800df8cc  mov     [rsp+0D60h+var_CF0], eax
0x1800df8d0  jz      loc_1800E03A4
0x1800df8d6  mov     rdx, 4000000000000800h; unsigned __int64
0x1800df8e0  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800df8e7  jz      loc_1800E03A4
0x1800df8ed  mov     rax, cs:qword_180169748
0x1800df8f4  and     rax, rdx
0x1800df8f7  cmp     cs:qword_180169748, rax
0x1800df8fe  jnz     loc_1800E03A4
0x1800df904  lea     rcx, [rbp+0C60h+var_9C0]; unsigned __int16 *
0x1800df90b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800df910  lea     rcx, [rbp+0C60h+var_9C0]
0x1800df917  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800df91b  inc     rax
0x1800df91e  cmp     [rcx+rax*2], di
0x1800df922  jnz     short loc_1800DF91B
0x1800df924  lea     ecx, [rax+rax]
0x1800df927  lea     rax, [rbp+0C60h+var_9C0]
0x1800df92e  jmp     loc_1800E033E
0x1800df933  mov     r8, qword ptr [rbp+0C60h+var_CD8+8]; unsigned __int16 *
0x1800df937  mov     eax, 8
0x1800df93c  mov     word ptr [rbp+0C60h+var_CD8], ax
0x1800df940  test    r8, r8
0x1800df943  jz      loc_1800E02CD
0x1800df949  cmp     di, [r8]
0x1800df94d  jz      loc_1800E02CD
0x1800df953  mov     edx, 400h; unsigned __int64
0x1800df958  mov     rcx, r15; unsigned __int16 *
0x1800df95b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800df960  mov     ebx, eax
0x1800df962  test    eax, eax
0x1800df964  jns     short loc_1800DF9D7
0x1800df966  cmp     dword ptr cs:xmmword_180169738, edi
0x1800df96c  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800df970  mov     [rsp+0D60h+var_CF0], eax
0x1800df974  jz      loc_1800E03A4
0x1800df97a  mov     rdx, 4000000000000800h; unsigned __int64
0x1800df984  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800df98b  jz      loc_1800E03A4
0x1800df991  mov     rax, cs:qword_180169748
0x1800df998  and     rax, rdx
0x1800df99b  cmp     cs:qword_180169748, rax
0x1800df9a2  jnz     loc_1800E03A4
0x1800df9a8  lea     rcx, [rbp+0C60h+var_940]; unsigned __int16 *
0x1800df9af  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800df9b4  lea     rcx, [rbp+0C60h+var_940]
0x1800df9bb  or      rax, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
