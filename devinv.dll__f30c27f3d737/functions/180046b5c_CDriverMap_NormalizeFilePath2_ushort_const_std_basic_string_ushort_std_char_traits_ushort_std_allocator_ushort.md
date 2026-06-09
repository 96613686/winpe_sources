# CDriverMap::NormalizeFilePath2(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180046b5c`
- end: `0x180047f59`
- name: `?NormalizeFilePath2@CDriverMap@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `5117`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, void *Src)`
- caller_count: `2`
- callee_count: `24`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18004255c`
- `0x18005d170`

## callees

- `0x180005960`
- `0x180005e40`
- `0x1800061f0`
- `0x18000642c`
- `0x180006494`
- `0x180006d02`
- `0x180006eb8`
- `0x180007014`
- `0x18000fa50`
- `0x180010368`
- `0x180010a9c`
- `0x180013f50`
- `0x180014b80`
- `0x180016440`
- `0x180017600`
- `0x180018e90`
- `0x18001dc84`
- `0x1800316a0`
- `0x180041e08`
- `0x180042028`
- `0x180046b5c`
- `0x1800488e4`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x180047141`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x1800471a6`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x180047b41`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x180047141`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x1800471a6`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x180047b41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046be9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046f44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047de7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046be9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046f44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047de7`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180046f36`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180046f36`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180046bd9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180046e0f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180046bd9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180046e0f`

## string_xrefs

- `0x180046c02`: `[0x%08x] NormalizeFilePath2 first pass ExpandEnvironmentStrings failed`
- `0x180046c12`: `CDriverMap::NormalizeFilePath2`
- `0x180046c41`: `CDriverMap::NormalizeFilePath2`
- `0x180046ce3`: `CDriverMap::NormalizeFilePath2`
- `0x180046d12`: `CDriverMap::NormalizeFilePath2`
- `0x180046f6f`: `CDriverMap::NormalizeFilePath2`
- `0x180046f95`: `CDriverMap::NormalizeFilePath2`
- `0x180047030`: `CDriverMap::NormalizeFilePath2`
- `0x180047056`: `CDriverMap::NormalizeFilePath2`
- `0x18004770d`: `CDriverMap::NormalizeFilePath2`
- `0x180047733`: `CDriverMap::NormalizeFilePath2`
- `0x1800479fc`: `CDriverMap::NormalizeFilePath2`
- `0x180047a22`: `CDriverMap::NormalizeFilePath2`
- `0x180047c3c`: `CDriverMap::NormalizeFilePath2`
- `0x180047c65`: `CDriverMap::NormalizeFilePath2`
- `0x180047e10`: `CDriverMap::NormalizeFilePath2`
- `0x180047e39`: `CDriverMap::NormalizeFilePath2`
- `0x180046cd3`: `NormalizeFilePath2 expansion exceeds MAX_PATH (required=%lu)`
- `0x180047e00`: `[0x%08x] NormalizeFilePath2 second pass ExpandEnvironmentStrings failed`
- `0x180046f5d`: `[0x%08x] NormalizeFilePath2 GetWindowsDirectory failed`
- `0x18004701e`: `NormalizeFilePath2 GetWindowsDirectory buffer too small`
- `0x1800472f3`: `system32\`
- `0x1800474e0`: `system32`
- `0x180047514`: `\systemroot\system32`
- `0x1800475f7`: `\system32`
- `0x1800478e6`: `\system32`
- `0x1800476fa`: `NormalizeFilePath2 directory-only system32 abbreviation`
- `0x1800479e9`: `NormalizeFilePath2 directory-only systemroot system32 abbreviation`
- `0x180047c2a`: `NormalizeFilePath2 invalid: trailing backslash [%ws]`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CDriverMap::NormalizeFilePath2(LPCWSTR lpSrc, _QWORD *Src, _QWORD *a3)
{
  _QWORD *v3; // rsi
  _QWORD *v4; // rbx
  _WORD *v6; // rcx
  _WORD *v7; // rcx
  DWORD v8; // eax
  DWORD v9; // edi
  signed int LastError; // eax
  unsigned int v11; // edi
  FILE *v12; // rax
  FILE *v13; // rax
  FILE *v14; // rax
  __int64 result; // rax
  FILE *v16; // rax
  FILE *v17; // rax
  FILE *v18; // rax
  LPWSTR *v19; // rcx
  __int64 v20; // r8
  WCHAR *v21; // rdx
  DWORD v22; // eax
  __int64 v23; // rax
  LPWSTR *i; // rcx
  unsigned __int64 v25; // rdx
  LPWSTR *v26; // r9
  _WORD *v27; // rdi
  WCHAR *v28; // r8
  __int64 v29; // rcx
  WCHAR *v30; // rdi
  WCHAR *v31; // rcx
  UINT WindowsDirectoryW; // eax
  signed int v33; // eax
  unsigned int v34; // edi
  FILE *v35; // rax
  FILE *v36; // rax
  FILE *v37; // rax
  FILE *v38; // rax
  FILE *v39; // rax
  FILE *v40; // rax
  LPWSTR *v41; // rcx
  wchar_t **v42; // rcx
  wchar_t **v43; // rdx
  wchar_t **v44; // rdi
  wchar_t **v45; // r15
  wchar_t **v46; // rcx
  wchar_t **v47; // rdx
  wchar_t **v48; // rdi
  wchar_t **v49; // r15
  __int64 v50; // r12
  const wchar_t *v51; // rdi
  size_t v52; // r13
  size_t v53; // r15
  const wchar_t *v54; // rcx
  size_t v55; // r8
  size_t v56; // rdx
  void **v57; // rcx
  size_t v58; // rdi
  size_t v59; // rdx
  wchar_t **v60; // rcx
  size_t v61; // rdi
  size_t v62; // rdi
  size_t v63; // r13
  const wchar_t *v64; // rdx
  size_t v65; // r15
  const wchar_t *v66; // rcx
  size_t v67; // r8
  wchar_t **v68; // rax
  size_t v69; // rcx
  const wchar_t *v70; // rdx
  size_t v71; // rdi
  wchar_t **v72; // rax
  const wchar_t *v73; // rcx
  size_t v74; // r8
  size_t v75; // rdx
  void **v76; // rcx
  size_t v77; // rdi
  size_t v78; // rdx
  wchar_t **v79; // rcx
  size_t v80; // rdi
  size_t v81; // r13
  const wchar_t *v82; // rdx
  size_t v83; // rdi
  const wchar_t *v84; // rcx
  size_t v85; // r8
  size_t v86; // rdi
  size_t v87; // rcx
  wchar_t **v88; // rax
  wchar_t *v89; // rdx
  bool v90; // zf
  size_t v91; // r13
  void **v92; // rax
  unsigned __int64 v93; // rcx
  _QWORD *v94; // rdx
  __int64 v95; // r8
  void **v96; // rax
  FILE *v97; // rax
  FILE *v98; // rax
  FILE *v99; // rax
  size_t v100; // r13
  const wchar_t *v101; // rdx
  size_t v102; // rdi
  const wchar_t *v103; // rcx
  size_t v104; // r8
  size_t v105; // rdi
  wchar_t **v106; // rax
  wchar_t *v107; // rdx
  bool v108; // zf
  size_t v109; // r13
  void **v110; // rax
  unsigned __int64 v111; // rcx
  _QWORD *v112; // rdx
  __int64 v113; // r8
  void **v114; // rax
  FILE *v115; // rax
  FILE *v116; // rax
  FILE *v117; // rax
  _QWORD *v118; // rcx
  _WORD *v119; // rdi
  _QWORD *v120; // rdx
  _WORD *v121; // r13
  __int64 v122; // rax
  _QWORD *v123; // r13
  __int64 v124; // rax
  char *v125; // rdi
  __int64 last_trivial_2; // rax
  __int64 v127; // rax
  unsigned __int64 v128; // rcx
  unsigned __int64 v129; // rax
  __int64 v130; // rcx
  _QWORD *v131; // rax
  FILE *v132; // rax
  _QWORD *v133; // rdi
  FILE *v134; // rax
  FILE *v135; // rax
  _QWORD *v136; // r8
  signed int v137; // eax
  unsigned int v138; // edi
  FILE *v139; // rax
  FILE *v140; // rax
  FILE *v141; // rax
  FILE *v142; // rax
  FILE *v143; // rax
  FILE *v144; // rax
  __int64 v145; // [rsp+30h] [rbp-168h] BYREF
  wchar_t *S1[2]; // [rsp+38h] [rbp-160h] BYREF
  size_t v147; // [rsp+48h] [rbp-150h]
  unsigned __int64 v148; // [rsp+50h] [rbp-148h]
  void *v149[2]; // [rsp+58h] [rbp-140h] BYREF
  size_t v150; // [rsp+68h] [rbp-130h]
  unsigned __int64 v151; // [rsp+70h] [rbp-128h]
  LPWSTR lpDst[2]; // [rsp+78h] [rbp-120h] BYREF
  unsigned __int64 v153; // [rsp+88h] [rbp-110h]
  unsigned __int64 v154; // [rsp+90h] [rbp-108h]
  LPWSTR lpBuffer[2]; // [rsp+98h] [rbp-100h] BYREF
  UINT uSize[2]; // [rsp+A8h] [rbp-F0h]
  unsigned __int64 v157; // [rsp+B0h] [rbp-E8h]
  wchar_t *S2[2]; // [rsp+B8h] [rbp-E0h] BYREF
  size_t N; // [rsp+C8h] [rbp-D0h]
  unsigned __int64 v160; // [rsp+D0h] [rbp-C8h]
  __int128 v161; // [rsp+D8h] [rbp-C0h] BYREF
  __int128 v162; // [rsp+E8h] [rbp-B0h]
  wchar_t *v163[2]; // [rsp+F8h] [rbp-A0h] BYREF
  size_t v164; // [rsp+108h] [rbp-90h]
  unsigned __int64 v165; // [rsp+110h] [rbp-88h]
  wchar_t *v166[2]; // [rsp+118h] [rbp-80h] BYREF
  size_t v167; // [rsp+128h] [rbp-70h]
  unsigned __int64 v168; // [rsp+130h] [rbp-68h]
  wchar_t *v169[2]; // [rsp+138h] [rbp-60h] BYREF
  size_t v170; // [rsp+148h] [rbp-50h]
  unsigned __int64 v171; // [rsp+150h] [rbp-48h]

  v3 = a3;
  v4 = Src;
  Src[2] = 0;
  if ( Src[3] <= 7u )
    v6 = Src;
  else
    v6 = (_WORD *)*Src;
  *v6 = 0;
  a3[2] = 0;
  if ( a3[3] <= 7u )
    v7 = a3;
  else
    v7 = (_WORD *)*a3;
  try
  {
    *v7 = 0;
    if ( !lpSrc || !*lpSrc )
      return 2147942487LL;
    v8 = ExpandEnvironmentStringsW(lpSrc, 0, 0);
    v9 = v8;
    if ( !v8 )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      AslLogCallPrintf(
        2,
        "CDriverMap::NormalizeFilePath2",
        2519,
        "[0x%08x] NormalizeFilePath2 first pass ExpandEnvironmentStrings failed",
        v11);
      if ( EnableDevInvStdErrLog )
      {
        v12 = o___acrt_iob_func_0(2u);
        fprintf(v12, "Error: %s, %u: ", "CDriverMap::NormalizeFilePath2", 2519);
        v13 = o___acrt_iob_func_0(2u);
        fprintf(v13, "[0x%08x] NormalizeFilePath2 first pass ExpandEnvironmentStrings failed", v11);
        v14 = o___acrt_iob_func_0(2u);
        fprintf(v14, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "[0x%08x] NormalizeFilePath2 first pass ExpandEnvironmentStrings failed", v11);
      v4[2] = 0;
      if ( v4[3] > 7u )
        v4 = (_QWORD *)*v4;
      *(_WORD *)v4 = 0;
      v3[2] = 0;
      if ( v3[3] > 7u )
        v3 = (_QWORD *)*v3;
      *(_WORD *)v3 = 0;
      return v11;
    }
    if ( v8 > 0x104 )
    {
      AslLogCallPrintf(
        2,
        "CDriverMap::NormalizeFilePath2",
        2528,
        "NormalizeFilePath2 expansion exceeds MAX_PATH (required=%lu)",
        v8);
      if ( EnableDevInvStdErrLog )
      {
        v16 = o___acrt_iob_func_0(2u);
        fprintf(v16, "Error: %s, %u: ", "CDriverMap::NormalizeFilePath2", 2528);
        v17 = o___acrt_iob_func_0(2u);
        fprintf(v17, "NormalizeFilePath2 expansion exceeds MAX_PATH (required=%lu)", v9);
        v18 = o___acrt_iob_func_0(2u);
        fprintf(v18, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "NormalizeFilePath2 expansion exceeds MAX_PATH (required=%lu)", v9);
      v4[2] = 0;
      if ( v4[3] > 7u )
        v4 = (_QWORD *)*v4;
      *(_WORD *)v4 = 0;
      v3[2] = 0;
      if ( v3[3] > 7u )
        v3 = (_QWORD *)*v3;
      *(_WORD *)v3 = 0;
      return 2147942487LL;
    }
    *(_OWORD *)lpDst = 0;
    v153 = 0;
    v154 = 7;
    LOWORD(lpDst[0]) = 0;
    v19 = lpDst;
    if ( v8 > 7uLL )
    {
      std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(lpDst);
    }
    else
    {
      v153 = v8;
      v20 = v8;
      do
      {
        *(_WORD *)v19 = 0;
        v19 = (LPWSTR *)((char *)v19 + 2);
        --v20;
      }
      while ( v20 );
      *((_WORD *)lpDst + v8) = 0;
    }
    v21 = (WCHAR *)lpDst;
    if ( v154 > 7 )
      v21 = lpDst[0];
    v22 = ExpandEnvironmentStringsW(lpSrc, v21, v9);
    if ( v22 && v22 <= v9 )
    {
      v23 = v22 - 1;
      i = (LPWSTR *)v153;
      if ( (unsigned int)v23 > v153 )
      {
        v25 = (unsigned int)v23 - v153;
        if ( v25 > v154 - v153 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(lpDst);
        }
        else
        {
          v153 = (unsigned int)v23;
          v26 = lpDst;
          if ( v154 > 7 )
            v26 = (LPWSTR *)lpDst[0];
          v27 = (_WORD *)v26 + (_QWORD)i;
          if ( v25 )
          {
            for ( i = (LPWSTR *)((unsigned int)v23 - (_QWORD)i); i; i = (LPWSTR *)((char *)i - 1) )
              *v27++ = 0;
          }
          *((_WORD *)v26 + (unsigned int)v23) = 0;
        }
      }
      else
      {
        v153 = (unsigned int)v23;
        i = lpDst;
        if ( v154 > 7 )
          i = (LPWSTR *)lpDst[0];
        *((_WORD *)i + v23) = 0;
      }
      *(_OWORD *)lpBuffer = 0;
      *(_QWORD *)uSize = 0;
      v157 = 0;
      v145 = 263;
      v28 = (WCHAR *)std::wstring::_Allocate_for_capacity<0>(i, &v145);
      lpBuffer[0] = v28;
      v29 = 260;
      *(_QWORD *)uSize = 260;
      v157 = v145;
      v30 = v28;
      while ( v29 )
      {
        *v30++ = 0;
        --v29;
      }
      v28[260] = 0;
      v31 = (WCHAR *)lpBuffer;
      if ( v157 > 7 )
        v31 = lpBuffer[0];
      WindowsDirectoryW = GetWindowsDirectoryW(v31, uSize[0]);
      if ( !WindowsDirectoryW )
      {
        v33 = GetLastError();
        v34 = v33;
        if ( v33 > 0 )
          v34 = (unsigned __int16)v33 | 0x80070000;
        AslLogCallPrintf(
          2,
          "CDriverMap::NormalizeFilePath2",
          2556,
          "[0x%08x] NormalizeFilePath2 GetWindowsDirectory failed",
          v34);
        if ( EnableDevInvStdErrLog )
        {
          v35 = o___acrt_iob_func_0(2u);
          fprintf(v35, "Error: %s, %u: ", "CDriverMap::NormalizeFilePath2", 2556);
          v36 = o___acrt_iob_func_0(2u);
          fprintf(v36, "[0x%08x] NormalizeFilePath2 GetWindowsDirectory failed", v34);
          v37 = o___acrt_iob_func_0(2u);
          fprintf(v37, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "[0x%08x] NormalizeFilePath2 GetWindowsDirectory failed", v34);
        std::wstring::~wstring(lpBuffer);
        std::wstring::~wstring(lpDst);
        return v34;
      }
      if ( (unsigned __int64)WindowsDirectoryW >= *(_QWORD *)uSize )
      {
        AslLogCallPrintf(
          2,
          "CDriverMap::NormalizeFilePath2",
          2562,
          "NormalizeFilePath2 GetWindowsDirectory buffer too small");
        if ( EnableDevInvStdErrLog )
        {
          v38 = o___acrt_iob_func_0(2u);
          fprintf(v38, "Error: %s, %u: ", "CDriverMap::NormalizeFilePath2", 2562);
          v39 = o___acrt_iob_func_0(2u);
          fprintf(v39, "NormalizeFilePath2 GetWindowsDirectory buffer too small");
          v40 = o___acrt_iob_func_0(2u);
          fprintf(v40, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "NormalizeFilePath2 GetWindowsDirectory buffer too small");
        std::wstring::~wstring(lpBuffer);
        std::wstring::~wstring(lpDst);
        return 2147942522LL;
      }
      *(_QWORD *)uSize = WindowsDirectoryW;
      v41 = lpBuffer;
      if ( v157 > 7 )
        v41 = (LPWSTR *)lpBuffer[0];
      *((_WORD *)v41 + WindowsDirectoryW) = 0;
      std::wstring::wstring(v149, lpDst);
      std::wstring::wstring(S1, v149);
      if ( v148 > 7 )
      {
        v42 = (wchar_t **)S1[0];
        v43 = (wchar_t **)S1[0];
      }
      else
      {
        v42 = S1;
        v43 = S1;
      }
      v44 = v42;
      v45 = (wchar_t **)((char *)v43 + 2 * v147);
      if ( v42 != v45 )
      {
        do
        {
          *(_WORD *)v44 = _o_tolower(*(unsigned __int16 *)v44);
          v44 = (wchar_t **)((char *)v44 + 2);
        }
        while ( v44 != v45 );
      }
      std::wstring::wstring(S2, lpBuffer);
      if ( v160 > 7 )
      {
        v46 = (wchar_t **)S2[0];
        v47 = (wchar_t **)S2[0];
      }
      else
      {
        v46 = S2;
        v47 = S2;
      }
      v48 = v46;
      v49 = (wchar_t **)((char *)v47 + 2 * N);
      if ( v46 != v49 )
      {
        do
        {
          *(_WORD *)v48 = _o_tolower(*(unsigned __int16 *)v48);
          v48 = (wchar_t **)((char *)v48 + 2);
        }
        while ( v48 != v49 );
      }
      if ( dword_180157D00 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                       + 4LL) )
      {
        Init_thread_header(&dword_180157D00);
        v50 = -1;
        if ( dword_180157D00 == -1 )
        {
          v51 = (const wchar_t *)&qword_180157D10;
          std::wstring::_Construct<1,unsigned short const *>(&qword_180157D10, L"\\??\\", 4);
          atexit(CDriverMap::NormalizeFilePath2_::_3_::_dynamic_atexit_destructor_for__drivePrefix__);
          Init_thread_footer(&dword_180157D00);
LABEL_87:
          v52 = ::N;
          if ( (unsigned __int64)qword_180157D28 > 7 )
            v51 = qword_180157D10;
          v53 = ::N;
          if ( v147 < ::N )
            v53 = v147;
          v54 = (const wchar_t *)S1;
          if ( v148 > 7 )
            v54 = S1[0];
          v55 = v53;
          if ( ::N < v53 )
            v55 = ::N;
          if ( !wmemcmp(v54, v51, v55) && v53 >= v52 && v53 <= v52 )
          {
            v56 = v150;
            if ( v150 >= ::N )
              v56 = ::N;
            v57 = v149;
            if ( v151 > 7 )
              v57 = (void **)v149[0];
            v58 = v150 - v56;
            memmove_0(v57, (char *)v57 + 2 * v56, 2 * (v150 - v56) + 2);
            v150 = v58;
            v59 = v147;
            if ( v147 >= ::N )
              v59 = ::N;
            v60 = S1;
            if ( v148 > 7 )
              v60 = (wchar_t **)S1[0];
            v61 = v147 - v59;
            memmove_0(v60, (char *)v60 + 2 * v59, 2 * (v147 - v59) + 2);
            v147 = v61;
          }
          *(_OWORD *)v169 = 0;
          v170 = 0;
          v171 = 0;
          std::wstring::_Construct<1,unsigned short const *>(v169, L"system32\\", 9);
          if ( CDriverMap::m_fProcessWow64 )
          {
            v62 = N;
            v63 = v170;
            if ( v147 > N + v170 )
            {
              v64 = (const wchar_t *)S2;
              if ( v160 > 7 )
                v64 = S2[0];
              v65 = N;
              if ( v147 < N )
                v65 = v147;
              v66 = (const wchar_t *)S1;
              if ( v148 > 7 )
                v66 = S1[0];
              v67 = v65;
              if ( N < v65 )
                v67 = N;
              if ( !wmemcmp(v66, v64, v67) && v65 >= v62 && v65 <= v62 )
              {
                v68 = S1;
                if ( v148 > 7 )
                  v68 = (wchar_t **)S1[0];
                if ( *((_WORD *)v68 + N) == 92 )
                {
                  v69 = N + 1;
                  if ( v147 < N + 1 )
                    std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
                  v70 = (const wchar_t *)v169;
                  if ( v171 > 7 )
                    v70 = v169[0];
                  v71 = v63;
                  if ( v147 - v69 < v63 )
                    v71 = v147 - v69;
                  v72 = S1;
                  if ( v148 > 7 )
                    v72 = (wchar_t **)S1[0];
                  v73 = (const wchar_t *)v72 + v69;
                  v74 = v71;
                  if ( v63 < v71 )
                    v74 = v63;
                  if ( !wmemcmp(v73, v70, v74) && v71 >= v63 && v71 <= v63 )
                  {
                    v75 = v150;
                    if ( v150 >= N + 1 )
                      v75 = N + 1;
                    v76 = v149;
                    if ( v151 > 7 )
                      v76 = (void **)v149[0];
                    v77 = v150 - v75;
                    memmove_0(v76, (char *)v76 + 2 * v75, 2 * (v150 - v75) + 2);
                    v150 = v77;
                    v78 = v147;
                    if ( v147 >= N + 1 )
                      v78 = N + 1;
                    v79 = S1;
                    if ( v148 > 7 )
                      v79 = (wchar_t **)S1[0];
                    v80 = v147 - v78;
                    memmove_0(v79, (char *)v79 + 2 * v78, 2 * (v147 - v78) + 2);
                    v147 = v80;
                  }
                }
              }
            }
          }
          *(_OWORD *)v166 = 0;
          v167 = 0;
          v168 = 0;
          std::wstring::_Construct<1,unsigned short const *>(v166, L"system32", 8);
          *(_OWORD *)v163 = 0;
          v164 = 0;
          v165 = 0;
          std::wstring::_Construct<1,unsigned short const *>(v163, L"\\systemroot\\system32", 20);
          v81 = v167;
          v82 = (const wchar_t *)v166;
          if ( v168 > 7 )
            v82 = v166[0];
          v83 = v167;
          if ( v147 < v167 )
            v83 = v147;
          v84 = (const wchar_t *)S1;
          if ( v148 > 7 )
            v84 = S1[0];
          v85 = v83;
          if ( v167 < v83 )
            v85 = v167;
          if ( !wmemcmp(v84, v82, v85) && v83 >= v81 && v83 <= v81 )
          {
            v86 = v167;
            v87 = v147;
            if ( v147 == v167 )
              goto LABEL_160;
            if ( v147 > v167 )
            {
              v88 = S1;
              if ( v148 > 7 )
                v88 = (wchar_t **)S1[0];
              if ( *((_WORD *)v88 + v167) == 92 )
              {
LABEL_160:
                std::wstring::reserve(v4, v150 + 32 + *(_QWORD *)uSize);
                std::wstring::append(v4);
                v89 = L"\\sysnative";
                if ( !CDriverMap::m_fProcessWow64 )
                  v89 = L"\\system32";
                std::wstring::append(v4, v89);
                v90 = v150 == v86;
                if ( v150 > v86 )
                {
                  v91 = v86;
                  v92 = v149;
                  if ( v151 > 7 )
                    v92 = (void **)v149[0];
                  if ( *((_WORD *)v92 + v86) == 92 )
                    v91 = v86 + 1;
                  v93 = v4[2];
                  if ( v93 >= v4[3] )
                  {
                    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v4);
                  }
                  else
                  {
                    v4[2] = v93 + 1;
                    if ( v4[3] <= 7u )
                      v94 = v4;
                    else
                      v94 = (_QWORD *)*v4;
                    *(_DWORD *)((char *)v94 + 2 * v93) = 92;
                  }
                  v161 = 0;
                  v162 = 0;
                  if ( v150 < v91 )
                    std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
                  v95 = -1;
                  if ( v150 - v91 != -1 )
                    v95 = v150 - v91;
                  v96 = v149;
                  if ( v151 > 7 )
                    v96 = (void **)v149[0];
                  std::wstring::_Construct<1,unsigned short const *>(&v161, (char *)v96 + 2 * v91, v95);
                  std::wstring::append(v4);
                  std::wstring::~wstring(&v161);
                  v90 = v150 == v86;
                }
                if ( v90 )
                {
                  AslLogCallPrintf(
                    2,
                    "CDriverMap::NormalizeFilePath2",
                    2644,
                    "NormalizeFilePath2 directory-only system32 abbreviation");
                  if ( EnableDevInvStdErrLog )
                  {
                    v97 = o___acrt_iob_func_0(2u);
                    fprintf(v97, "Error: %s, %u: ", "CDriverMap::NormalizeFilePath2", 2644);
                    v98 = o___acrt_iob_func_0(2u);
                    fprintf(v98, "NormalizeFilePath2 directory-only system32 abbreviation");
                    v99 = o___acrt_iob_func_0(2u);
                    fprintf(v99, "\n");
                  }
                  if ( g_DeviceMapLogFunction )
                    TraceMessageCallback(0x2000000, "NormalizeFilePath2 directory-only system32 abbreviation");
                  v4[2] = 0;
                  if ( v4[3] > 7u )
                    v4 = (_QWORD *)*v4;
                  *(_WORD *)v4 = 0;
                  v3[2] = 0;
                  if ( v3[3] > 7u )
                    v3 = (_QWORD *)*v3;
LABEL_272:
                  *(_WORD *)v3 = 0;
                  std::wstring::~wstring(v163);
                  std::wstring::~wstring(v166);
                  std::wstring::~wstring(v169);
                  std::wstring::~wstring(S2);
                  std::wstring::~wstring(S1);
                  std::wstring::~wstring(v149);
                  std::wstring::~wstring(lpBuffer);
                  std::wstring::~wstring(lpDst);
                  return 2147942487LL;
                }
LABEL_236:
                if ( v4[3] > 7u )
                {
                  v118 = (_QWORD *)*v4;
                  v119 = (_WORD *)*v4;
                  v120 = (_QWORD *)*v4;
                }
                else
                {
                  v118 = v4;
                  v119 = v4;
                  v120 = v4;
                }
                v121 = (_WORD *)v120 + v4[2];
                if ( v118 != (_QWORD *)v121 )
                {
                  do
                  {
                    *v119 = _o_tolower((unsigned __int16)*v119);
                    ++v119;
                  }
                  while ( v119 != v121 );
                }
                v122 = v4[2];
                if ( v4[3] <= 7u )
                  v123 = v4;
                else
                  v123 = (_QWORD *)*v4;
                if ( !v122 )
                  goto LABEL_273;
                v124 = v122 - 1;
                if ( v124 == -1 )
                  v124 = -1;
                v125 = (char *)v123 + 2 * v124 + 2;
                last_trivial_2 = _std_find_last_trivial_2(v123, v125, 92);
                if ( (char *)last_trivial_2 == v125 || (v127 = (last_trivial_2 - (__int64)v123) >> 1, v127 == -1) )
                {
LABEL_273:
                  std::wstring::operator=(v3, v4);
                }
                else
                {
                  v128 = v4[2];
                  v129 = v127 + 1;
                  if ( v129 >= v128 )
                  {
                    if ( v4[3] <= 7u )
                      v131 = v4;
                    else
                      v131 = (_QWORD *)*v4;
                    AslLogCallPrintf(
                      2,
                      "CDriverMap::NormalizeFilePath2",
                      2701,
                      "NormalizeFilePath2 invalid: trailing backslash [%ws]",
                      v131);
                    if ( EnableDevInvStdErrLog )
                    {
                      v132 = o___acrt_iob_func_0(2u);
                      fprintf(v132, "Error: %s, %u: ", "CDriverMap::NormalizeFilePath2", 2701);
                      if ( v4[3] <= 7u )
                        v133 = v4;
                      else
                        v133 = (_QWORD *)*v4;
                      v134 = o___acrt_iob_func_0(2u);
                      fprintf(v134, "NormalizeFilePath2 invalid: trailing backslash [%ws]", v133);
                      v135 = o___acrt_iob_func_0(2u);
                      fprintf(v135, "\n");
                    }
                    if ( g_DeviceMapLogFunction )
                    {
                      if ( v4[3] <= 7u )
                        v136 = v4;
                      else
                        v136 = (_QWORD *)*v4;
                      TraceMessageCallback(0x2000000, "NormalizeFilePath2 invalid: trailing backslash [%ws]", v136);
                    }
                    v4[2] = 0;
                    if ( v4[3] > 7u )
                      v4 = (_QWORD *)*v4;
                    *(_WORD *)v4 = 0;
                    v3[2] = 0;
                    if ( v3[3] > 7u )
                      v3 = (_QWORD *)*v3;
                    goto LABEL_272;
                  }
                  v161 = 0;
                  v162 = 0;
                  v130 = v128 - v129;
                  if ( v130 != -1 )
                    v50 = v130;
                  if ( v4[3] > 7u )
                    v4 = (_QWORD *)*v4;
                  std::wstring::_Construct<1,unsigned short const *>(&v161, (char *)v4 + 2 * v129, v50);
                  std::wstring::operator=(v3, &v161);
                  std::wstring::~wstring(&v161);
                }
                std::wstring::~wstring(v163);
                std::wstring::~wstring(v166);
                std::wstring::~wstring(v169);
                std::wstring::~wstring(S2);
                std::wstring::~wstring(S1);
                std::wstring::~wstring(v149);
                std::wstring::~wstring(lpBuffer);
                std::wstring::~wstring(lpDst);
                return 0;
              }
            }
          }
          else
          {
            v87 = v147;
          }
          v100 = v164;
          v101 = (const wchar_t *)v163;
          if ( v165 > 7 )
            v101 = v163[0];
          v102 = v164;
          if ( v87 < v164 )
            v102 = v87;
          v103 = (const wchar_t *)S1;
          if ( v148 > 7 )
            v103 = S1[0];
          v104 = v102;
          if ( v164 < v102 )
            v104 = v164;
          if ( wmemcmp(v103, v101, v104) || v102 < v100 || v102 > v100 )
            goto LABEL_235;
          v105 = v164;
          if ( v147 == v164 )
            goto LABEL_206;
          if ( v147 <= v164 )
            goto LABEL_235;
          v106 = S1;
          if ( v148 > 7 )
            v106 = (wchar_t **)S1[0];
          if ( *((_WORD *)v106 + v164) == 92 )
          {
LABEL_206:
            std::wstring::reserve(v4, v150 + 32 + *(_QWORD *)uSize);
            std::wstring::append(v4);
            v107 = L"\\sysnative";
            if ( !CDriverMap::m_fProcessWow64 )
              v107 = L"\\system32";
            std::wstring::append(v4, v107);
            v108 = v150 == v105;
            if ( v150 > v105 )
            {
              v109 = v105;
              v110 = v149;
              if ( v151 > 7 )
                v110 = (void **)v149[0];
              if ( *((_WORD *)v110 + v105) == 92 )
                v109 = v105 + 1;
              v111 = v4[2];
              if ( v111 >= v4[3] )
              {
                std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v4);
              }
              else
              {
                v4[2] = v111 + 1;
                if ( v4[3] <= 7u )
                  v112 = v4;
                else
                  v112 = (_QWORD *)*v4;
                *(_DWORD *)((char *)v112 + 2 * v111) = 92;
              }
              v161 = 0;
              v162 = 0;
              if ( v150 < v109 )
                std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
              v113 = -1;
              if ( v150 - v109 != -1 )
                v113 = v150 - v109;
              v114 = v149;
              if ( v151 > 7 )
                v114 = (void **)v149[0];
              std::wstring::_Construct<1,unsigned short const *>(&v161, (char *)v114 + 2 * v109, v113);
              std::wstring::append(v4);
              std::wstring::~wstring(&v161);
              v108 = v150 == v105;
            }
            if ( v108 )
            {
              AslLogCallPrintf(
                2,
                "CDriverMap::NormalizeFilePath2",
                2672,
                "NormalizeFilePath2 directory-only systemroot system32 abbreviation");
              if ( EnableDevInvStdErrLog )
              {
                v115 = o___acrt_iob_func_0(2u);
                fprintf(v115, "Error: %s, %u: ", "CDriverMap::NormalizeFilePath2", 2672);
                v116 = o___acrt_iob_func_0(2u);
                fprintf(v116, "NormalizeFilePath2 directory-only systemroot system32 abbreviation");
                v117 = o___acrt_iob_func_0(2u);
                fprintf(v117, "\n");
              }
              if ( g_DeviceMapLogFunction )
                TraceMessageCallback(0x2000000, "NormalizeFilePath2 directory-only systemroot system32 abbreviation");
              v4[2] = 0;
              if ( v4[3] > 7u )
                v4 = (_QWORD *)*v4;
              *(_WORD *)v4 = 0;
              v3[2] = 0;
              if ( v3[3] > 7u )
                v3 = (_QWORD *)*v3;
              goto LABEL_272;
            }
          }
          else
          {
LABEL_235:
            std::wstring::operator=(v4, v149);
          }
          goto LABEL_236;
        }
      }
      else
      {
        v50 = -1;
      }
      v51 = (const wchar_t *)&qword_180157D10;
      goto LABEL_87;
    }
    v137 = GetLastError();
    v138 = v137;
    if ( v137 > 0 )
      v138 = (unsigned __int16)v137 | 0x80070000;
    AslLogCallPrintf(
      2,
      "CDriverMap::NormalizeFilePath2",
      2541,
      "[0x%08x] NormalizeFilePath2 second pass ExpandEnvironmentStrings failed",
      v138);
    if ( EnableDevInvStdErrLog )
    {
      v139 = o___acrt_iob_func_0(2u);
      fprintf(v139, "Error: %s, %u: ", "CDriverMap::NormalizeFilePath2", 2541);
      v140 = o___acrt_iob_func_0(2u);
      fprintf(v140, "[0x%08x] NormalizeFilePath2 second pass ExpandEnvironmentStrings failed", v138);
      v141 = o___acrt_iob_func_0(2u);
      fprintf(v141, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "[0x%08x] NormalizeFilePath2 second pass ExpandEnvironmentStrings failed", v138);
    v4[2] = 0;
    if ( v4[3] > 7u )
      v4 = (_QWORD *)*v4;
    *(_WORD *)v4 = 0;
    v3[2] = 0;
    if ( v3[3] > 7u )
      v3 = (_QWORD *)*v3;
    *(_WORD *)v3 = 0;
    std::wstring::~wstring(lpDst);
    result = v138;
  }
  catch ( std::bad_alloc )
  {
    AslLogCallPrintf(2, "CDriverMap::NormalizeFilePath2", 2709, "Out of memory");
    if ( EnableDevInvStdErrLog )
    {
      v142 = o___acrt_iob_func_0(2u);
      fprintf(v142, "Error: %s, %u: ", "CDriverMap::NormalizeFilePath2", 2709);
      v143 = o___acrt_iob_func_0(2u);
      fprintf(v143, "Out of memory");
      v144 = o___acrt_iob_func_0(2u);
      fprintf(v144, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "Out of memory");
    return 2147942408LL;
  }
  return result;
}

```

## disassembly

```asm
0x180046b5c  push    rbx
0x180046b5e  push    rsi
0x180046b5f  push    rdi
0x180046b60  push    r12
0x180046b62  push    r13
0x180046b64  push    r14
0x180046b66  push    r15
0x180046b68  sub     rsp, 160h
0x180046b6f  mov     rax, cs:__security_cookie
0x180046b76  xor     rax, rsp
0x180046b79  mov     [rsp+198h+var_40], rax
0x180046b81  mov     rsi, r8
0x180046b84  mov     rbx, rdx
0x180046b87  mov     r15, rcx
0x180046b8a  xor     r12d, r12d
0x180046b8d  mov     [rdx+10h], r12
0x180046b91  lea     r13d, [r12+7]
0x180046b96  cmp     [rdx+18h], r13
0x180046b9a  jbe     short loc_180046BA1
0x180046b9c  mov     rcx, [rdx]
0x180046b9f  jmp     short loc_180046BA4
0x180046ba1  mov     rcx, rbx
0x180046ba4  mov     [rcx], r12w
0x180046ba8  mov     [r8+10h], r12
0x180046bac  cmp     [r8+18h], r13
0x180046bb0  jbe     short loc_180046BB7
0x180046bb2  mov     rcx, [r8]
0x180046bb5  jmp     short loc_180046BBA
0x180046bb7  mov     rcx, rsi
0x180046bba  mov     [rcx], r12w
0x180046bbe  test    r15, r15
0x180046bc1  jz      loc_180047EC2
0x180046bc7  cmp     [r15], r12w
0x180046bcb  jz      loc_180047EC2
0x180046bd1  xor     r8d, r8d; nSize
0x180046bd4  xor     edx, edx; lpDst
0x180046bd6  mov     rcx, r15; lpSrc
0x180046bd9  call    cs:__imp_ExpandEnvironmentStringsW
0x180046bdf  mov     edi, eax
0x180046be1  test    eax, eax
0x180046be3  jnz     loc_180046CC3
0x180046be9  call    cs:__imp_GetLastError
0x180046bef  mov     edi, eax
0x180046bf1  test    eax, eax
0x180046bf3  jle     short loc_180046BFE
0x180046bf5  movzx   edi, ax
0x180046bf8  or      edi, 80070000h
0x180046bfe  mov     dword ptr [rsp+198h+var_178], edi
0x180046c02  lea     r15, a0x08xNormalize; "[0x%08x] NormalizeFilePath2 first pass "...
0x180046c09  mov     r9, r15
0x180046c0c  mov     r8d, 9D7h
0x180046c12  lea     rdx, aCdrivermapNorm; "CDriverMap::NormalizeFilePath2"
0x180046c19  mov     r14d, 2
0x180046c1f  mov     ecx, r14d
0x180046c22  call    AslLogCallPrintf
0x180046c27  cmp     cs:EnableDevInvStdErrLog, r12d
0x180046c2e  jz      short loc_180046C81
0x180046c30  mov     ecx, r14d; Ix
0x180046c33  call    _o___acrt_iob_func_0
0x180046c38  mov     rcx, rax; Stream
0x180046c3b  mov     r9d, 9D7h
0x180046c41  lea     r8, aCdrivermapNorm; "CDriverMap::NormalizeFilePath2"
0x180046c48  lea     rdx, Format; "Error: %s, %u: "
0x180046c4f  call    fprintf
0x180046c54  mov     ecx, r14d; Ix
0x180046c57  call    _o___acrt_iob_func_0
0x180046c5c  mov     rcx, rax; Stream
0x180046c5f  mov     r8d, edi
0x180046c62  mov     rdx, r15; Format
0x180046c65  call    fprintf
0x180046c6a  mov     ecx, r14d; Ix
0x180046c6d  call    _o___acrt_iob_func_0
0x180046c72  mov     rcx, rax; Stream
0x180046c75  lea     rdx, asc_18011EAD8; "\n"
0x180046c7c  call    fprintf
0x180046c81  cmp     cs:g_DeviceMapLogFunction, r12
0x180046c88  jz      short loc_180046C9A
0x180046c8a  mov     r8d, edi
0x180046c8d  mov     rdx, r15
0x180046c90  mov     ecx, 2000000h
0x180046c95  call    TraceMessageCallback
0x180046c9a  mov     [rbx+10h], r12
0x180046c9e  cmp     [rbx+18h], r13
0x180046ca2  jbe     short loc_180046CA7
0x180046ca4  mov     rbx, [rbx]
0x180046ca7  mov     [rbx], r12w
0x180046cab  mov     [rsi+10h], r12
0x180046caf  cmp     [rsi+18h], r13
0x180046cb3  jbe     short loc_180046CB8
0x180046cb5  mov     rsi, [rsi]
0x180046cb8  mov     [rsi], r12w
0x180046cbc  mov     eax, edi
0x180046cbe  jmp     loc_180047ECE
0x180046cc3  cmp     edi, 104h
0x180046cc9  jbe     loc_180046D97
0x180046ccf  mov     dword ptr [rsp+198h+var_178], edi
0x180046cd3  lea     r15, aNormalizefilep_3; "NormalizeFilePath2 expansion exceeds MA"...
0x180046cda  mov     r9, r15
0x180046cdd  mov     r8d, 9E0h
0x180046ce3  lea     rdx, aCdrivermapNorm; "CDriverMap::NormalizeFilePath2"
0x180046cea  mov     r14d, 2
0x180046cf0  mov     ecx, r14d
0x180046cf3  call    AslLogCallPrintf
0x180046cf8  cmp     cs:EnableDevInvStdErrLog, r12d
0x180046cff  jz      short loc_180046D52
0x180046d01  mov     ecx, r14d; Ix
0x180046d04  call    _o___acrt_iob_func_0
0x180046d09  mov     rcx, rax; Stream
0x180046d0c  mov     r9d, 9E0h
0x180046d12  lea     r8, aCdrivermapNorm; "CDriverMap::NormalizeFilePath2"
0x180046d19  lea     rdx, Format; "Error: %s, %u: "
0x180046d20  call    fprintf
0x180046d25  mov     ecx, r14d; Ix
0x180046d28  call    _o___acrt_iob_func_0
0x180046d2d  mov     rcx, rax; Stream
0x180046d30  mov     r8d, edi
0x180046d33  mov     rdx, r15; Format
0x180046d36  call    fprintf
0x180046d3b  mov     ecx, r14d; Ix
0x180046d3e  call    _o___acrt_iob_func_0
0x180046d43  mov     rcx, rax; Stream
0x180046d46  lea     rdx, asc_18011EAD8; "\n"
0x180046d4d  call    fprintf
0x180046d52  cmp     cs:g_DeviceMapLogFunction, r12
0x180046d59  jz      short loc_180046D6B
0x180046d5b  mov     r8d, edi
0x180046d5e  mov     rdx, r15
0x180046d61  mov     ecx, 2000000h
0x180046d66  call    TraceMessageCallback
0x180046d6b  mov     [rbx+10h], r12
0x180046d6f  cmp     [rbx+18h], r13
0x180046d73  jbe     short loc_180046D78
0x180046d75  mov     rbx, [rbx]
0x180046d78  mov     [rbx], r12w
0x180046d7c  mov     [rsi+10h], r12
0x180046d80  cmp     [rsi+18h], r13
0x180046d84  jbe     short loc_180046D89
0x180046d86  mov     rsi, [rsi]
0x180046d89  mov     [rsi], r12w
0x180046d8d  mov     eax, 80070057h
0x180046d92  jmp     loc_180047ECE
0x180046d97  xorps   xmm0, xmm0
0x180046d9a  movups  xmmword ptr [rsp+198h+lpDst], xmm0
0x180046d9f  mov     [rsp+198h+var_110], r12
0x180046da7  mov     [rsp+198h+var_108], r13
0x180046daf  mov     word ptr [rsp+198h+lpDst], r12w
0x180046db5  mov     rdx, rdi
0x180046db8  lea     rcx, [rsp+198h+lpDst]; Src
0x180046dbd  cmp     rdi, r13
0x180046dc0  ja      short loc_180046DE8
0x180046dc2  mov     [rsp+198h+var_110], rdx
0x180046dca  mov     r8, rdx
0x180046dcd  mov     r14d, 2
0x180046dd3  mov     [rcx], r12w
0x180046dd7  add     rcx, r14
0x180046dda  sub     r8, 1
0x180046dde  jnz     short loc_180046DD3
0x180046de0  mov     word ptr [rsp+rdi*2+198h+lpDst], r12w
0x180046de6  jmp     short loc_180046DF6
0x180046de8  mov     r9, rdx
0x180046deb  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x180046df0  mov     r14d, 2
0x180046df6  lea     rdx, [rsp+198h+lpDst]
0x180046dfb  cmp     [rsp+198h+var_108], r13
0x180046e03  cmova   rdx, [rsp+198h+lpDst]; lpDst
0x180046e09  mov     r8d, edi; nSize
0x180046e0c  mov     rcx, r15; lpSrc
0x180046e0f  call    cs:__imp_ExpandEnvironmentStringsW
0x180046e15  test    eax, eax
0x180046e17  jz      loc_180047DE7
0x180046e1d  cmp     eax, edi
0x180046e1f  ja      loc_180047DE7
0x180046e25  dec     eax
0x180046e27  mov     r8d, eax
0x180046e2a  mov     rcx, [rsp+198h+var_110]
0x180046e32  cmp     r8, rcx
0x180046e35  ja      short loc_180046E59
0x180046e37  mov     [rsp+198h+var_110], r8
0x180046e3f  lea     rcx, [rsp+198h+lpDst]
0x180046e44  cmp     [rsp+198h+var_108], r13
0x180046e4c  cmova   rcx, [rsp+198h+lpDst]
0x180046e52  mov     [rcx+rax*2], r12w
0x180046e57  jmp     short loc_180046EB1
0x180046e59  mov     rdx, r8
0x180046e5c  sub     rdx, rcx
0x180046e5f  mov     rax, [rsp+198h+var_108]
0x180046e67  sub     rax, rcx
0x180046e6a  cmp     rdx, rax
0x180046e6d  ja      short loc_180046EA4
0x180046e6f  mov     [rsp+198h+var_110], r8
0x180046e77  lea     r9, [rsp+198h+lpDst]
0x180046e7c  cmp     [rsp+198h+var_108], r13
0x180046e84  cmova   r9, [rsp+198h+lpDst]
0x180046e8a  lea     rdi, [r9+rcx*2]
0x180046e8e  test    rdx, rdx
0x180046e91  jz      short loc_180046E9D
0x180046e93  movzx   eax, r12w
0x180046e97  mov     rcx, rdx
0x180046e9a  rep stosw
0x180046e9d  mov     [r9+r8*2], r12w
0x180046ea2  jmp     short loc_180046EB1
0x180046ea4  mov     r9, rdx
0x180046ea7  lea     rcx, [rsp+198h+lpDst]; Src
0x180046eac  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x180046eb1  xorps   xmm0, xmm0
0x180046eb4  movups  xmmword ptr [rsp+198h+lpBuffer], xmm0
0x180046ebc  mov     qword ptr [rsp+198h+uSize], r12
0x180046ec4  mov     [rsp+198h+var_E8], r12
0x180046ecc  mov     [rsp+198h+var_168], 107h
0x180046ed5  lea     rdx, [rsp+198h+var_168]
0x180046eda  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180046edf  mov     r8, rax
0x180046ee2  mov     [rsp+198h+lpBuffer], rax
0x180046eea  mov     ecx, 104h
0x180046eef  mov     qword ptr [rsp+198h+uSize], rcx
0x180046ef7  mov     rdx, [rsp+198h+var_168]
0x180046efc  mov     [rsp+198h+var_E8], rdx
0x180046f04  movzx   eax, r12w
0x180046f08  mov     rdi, r8
0x180046f0b  rep stosw
0x180046f0e  mov     [r8+208h], r12w
0x180046f16  lea     rcx, [rsp+198h+lpBuffer]
0x180046f1e  cmp     [rsp+198h+var_E8], r13
0x180046f26  cmova   rcx, [rsp+198h+lpBuffer]; lpBuffer
0x180046f2f  mov     edx, [rsp+198h+uSize]; uSize
0x180046f36  call    cs:__imp_GetWindowsDirectoryW
0x180046f3c  test    eax, eax
0x180046f3e  jnz     loc_18004700E
0x180046f44  call    cs:__imp_GetLastError
0x180046f4a  mov     edi, eax
0x180046f4c  test    eax, eax
0x180046f4e  jle     short loc_180046F59
0x180046f50  movzx   edi, ax
0x180046f53  or      edi, 80070000h
0x180046f59  mov     dword ptr [rsp+198h+var_178], edi
0x180046f5d  lea     rbx, a0x08xNormalize_0; "[0x%08x] NormalizeFilePath2 GetWindowsD"...
0x180046f64  mov     r9, rbx
0x180046f67  mov     esi, 9FCh
0x180046f6c  mov     r8d, esi
0x180046f6f  lea     rdx, aCdrivermapNorm; "CDriverMap::NormalizeFilePath2"
0x180046f76  mov     ecx, r14d
0x180046f79  call    AslLogCallPrintf
0x180046f7e  cmp     cs:EnableDevInvStdErrLog, r12d
0x180046f85  jz      short loc_180046FD5
0x180046f87  mov     ecx, r14d; Ix
0x180046f8a  call    _o___acrt_iob_func_0
0x180046f8f  mov     rcx, rax; Stream
0x180046f92  mov     r9d, esi
0x180046f95  lea     r8, aCdrivermapNorm; "CDriverMap::NormalizeFilePath2"
0x180046f9c  lea     rdx, Format; "Error: %s, %u: "
0x180046fa3  call    fprintf
0x180046fa8  mov     ecx, r14d; Ix
0x180046fab  call    _o___acrt_iob_func_0
0x180046fb0  mov     rcx, rax; Stream
0x180046fb3  mov     r8d, edi
0x180046fb6  mov     rdx, rbx; Format
0x180046fb9  call    fprintf
0x180046fbe  mov     ecx, r14d; Ix
0x180046fc1  call    _o___acrt_iob_func_0
0x180046fc6  mov     rcx, rax; Stream
0x180046fc9  lea     rdx, asc_18011EAD8; "\n"
0x180046fd0  call    fprintf
0x180046fd5  cmp     cs:g_DeviceMapLogFunction, r12
0x180046fdc  jz      short loc_180046FEF
0x180046fde  mov     r8d, edi
0x180046fe1  mov     rdx, rbx
0x180046fe4  mov     ecx, 2000000h
0x180046fe9  call    TraceMessageCallback
0x180046fee  nop
0x180046fef  lea     rcx, [rsp+198h+lpBuffer]; void *
0x180046ff7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180046ffc  nop
0x180046ffd  lea     rcx, [rsp+198h+lpDst]; void *
0x180047002  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180047007  mov     eax, edi
0x180047009  jmp     loc_180047ECE
0x18004700e  mov     edx, eax
0x180047010  cmp     rdx, qword ptr [rsp+198h+uSize]
0x180047018  jb      loc_1800470CC
0x18004701e  lea     rdi, aNormalizefilep_0; "NormalizeFilePath2 GetWindowsDirectory "...
0x180047025  mov     r9, rdi
0x180047028  mov     ebx, 0A02h
0x18004702d  mov     r8d, ebx
0x180047030  lea     rdx, aCdrivermapNorm; "CDriverMap::NormalizeFilePath2"
0x180047037  mov     ecx, r14d
0x18004703a  call    AslLogCallPrintf
0x18004703f  cmp     cs:EnableDevInvStdErrLog, r12d
0x180047046  jz      short loc_180047093
0x180047048  mov     ecx, r14d; Ix
0x18004704b  call    _o___acrt_iob_func_0
0x180047050  mov     rcx, rax; Stream
0x180047053  mov     r9d, ebx
0x180047056  lea     r8, aCdrivermapNorm; "CDriverMap::NormalizeFilePath2"
0x18004705d  lea     rdx, Format; "Error: %s, %u: "
0x180047064  call    fprintf
0x180047069  mov     ecx, r14d; Ix
0x18004706c  call    _o___acrt_iob_func_0
0x180047071  mov     rcx, rax; Stream
0x180047074  mov     rdx, rdi; Format
0x180047077  call    fprintf
  ... truncated ...
```
