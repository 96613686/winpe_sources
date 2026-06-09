# PlaliGetLogFileName(ulong,_PDH_PLALI_INFO_W *,ulong *,ushort *)

- ea: `0x1801303ec`
- end: `0x180130b20`
- name: `?PlaliGetLogFileName@@YAJKPEAU_PDH_PLALI_INFO_W@@PEAKPEAG@Z`
- size: `1844`
- prototype: `__int64 __fastcall(unsigned int, struct _PDH_PLALI_INFO_W *, unsigned int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180130b28`

## callees

- `0x180015f98`
- `0x180046c60`
- `0x180114300`
- `0x180116404`
- `0x18012f320`
- `0x1801303ec`
- `0x18013161c`
- `0x180131c14`
- `0x18013aee0`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x180130618`
- `msvcrt!_wsplitpath_s` at `0x180130618`
- `msvcrt!wcsstr` at `0x1801304c6`
- `msvcrt!wcsstr` at `0x1801304c6`
- `msvcrt!_wcsicmp` at `0x18013062c`
- `msvcrt!_wcsicmp` at `0x180130646`
- `msvcrt!_wcsicmp` at `0x18013065e`
- `msvcrt!_wcsicmp` at `0x180130676`
- `msvcrt!_wcsicmp` at `0x18013062c`
- `msvcrt!_wcsicmp` at `0x180130646`
- `msvcrt!_wcsicmp` at `0x18013065e`
- `msvcrt!_wcsicmp` at `0x180130676`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180130436`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180130436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180130a6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180130a6b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180130712`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180130712`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180130701`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180130ad9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180130701`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180130ad9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180130ae7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180130ae7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180130a61`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180130a61`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180130547`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180130547`

## pseudocode

```c
__int64 __fastcall PlaliGetLogFileName(char a1, struct _PDH_PLALI_INFO_W *a2, unsigned int *a3, unsigned __int16 *a4)
{
  unsigned __int64 v5; // r13
  unsigned __int16 *v6; // r12
  const unsigned __int16 *v7; // r14
  const wchar_t *v8; // rcx
  int v9; // r8d
  int v10; // esi
  int v11; // edi
  wchar_t *v12; // rax
  int IsStringEmpty; // eax
  __int64 v14; // r8
  unsigned __int64 v15; // rcx
  const unsigned __int16 *v16; // rcx
  const wchar_t *v17; // rdi
  unsigned int v18; // ebx
  __int16 v19; // r8
  __int64 v20; // rcx
  const unsigned __int16 *v21; // rax
  size_t v22; // r8
  unsigned __int64 v23; // rax
  __int64 v24; // rax
  unsigned int v25; // eax
  unsigned int v26; // ecx
  __int64 v27; // rax
  unsigned int v28; // eax
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v30; // rdi
  int v31; // eax
  char v32; // bl
  DWORD v33; // r12d
  unsigned __int16 *v34; // r8
  int wDay; // eax
  const unsigned __int16 *v36; // r8
  int wMonth; // ecx
  int wYear; // edx
  struct _SYSTEMTIME v39; // xmm0
  const unsigned __int16 *v40; // r8
  unsigned __int16 *v41; // rsi
  int v42; // r14d
  DWORD v43; // eax
  DWORD LastError; // eax
  __int64 v45; // rcx
  unsigned __int16 *v46; // r11
  HANDLE v47; // rax
  size_t ExtCount; // [rsp+40h] [rbp-C0h]
  int DayOfYear; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v51; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v52; // [rsp+68h] [rbp-98h]
  const size_t *v53; // [rsp+70h] [rbp-90h]
  struct _SYSTEMTIME v57; // [rsp+90h] [rbp-70h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v59[128]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t String1[256]; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t Filename[256]; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned __int16 v62[264]; // [rsp+5B0h] [rbp+4B0h] BYREF

  SystemTime = 0;
  GetLocalTime(&SystemTime);
  LODWORD(v5) = 0;
  v52 = L"_";
  v6 = 0;
  v7 = 0;
  if ( (*(_BYTE *)a2 & 0x10) != 0 )
    v6 = (unsigned __int16 *)*((_QWORD *)a2 + 7);
  if ( (*(_DWORD *)a2 & 0x2000) != 0 )
    v7 = (const unsigned __int16 *)*((_QWORD *)a2 + 6);
  if ( (*(_BYTE *)a2 & 2) == 0 || *((_DWORD *)a2 + 18) != 6 )
  {
    v51 = L"\\";
    if ( (unsigned int)PlaliIsStringEmpty(v7) )
    {
      v7 = L"%SystemDrive%\\PerfLogs";
    }
    else
    {
      v20 = -1;
      do
        ++v20;
      while ( v7[v20] != v19 );
      v21 = (const unsigned __int16 *)&szPassword;
      if ( v7[v20 - 1] != 92 )
        v21 = L"\\";
      v51 = v21;
    }
    if ( (unsigned int)PlaliIsStringEmpty(v6) )
    {
      if ( (*(_BYTE *)a2 & 0x20) != 0 && *((_DWORD *)a2 + 19) == -1 )
        goto LABEL_27;
      v6 = (unsigned __int16 *)&szPassword;
      v52 = (const unsigned __int16 *)&szPassword;
    }
    v53 = &szPassword;
    _wsplitpath_s(v6, 0, v22, 0, v22, Filename, 0x100u, String1, 0x100u);
    if ( _wcsicmp(String1, L".etl")
      && _wcsicmp(String1, L".blg")
      && _wcsicmp(String1, L".csv")
      && _wcsicmp(String1, L".tsv") )
    {
      goto LABEL_47;
    }
    v23 = -1;
    do
      ++v23;
    while ( Filename[v23] );
    if ( v23 >= 0x104 )
    {
LABEL_47:
      if ( !v6 )
      {
        v25 = 0;
LABEL_52:
        v26 = v25 >> 1;
        if ( v7 )
        {
          v27 = -1;
          do
            ++v27;
          while ( v7[v27] );
          v28 = 2 * v27;
        }
        else
        {
          v28 = 0;
        }
        v5 = v26 + (v28 >> 1) + 32;
        ProcessHeap = GetProcessHeap();
        v30 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v5);
        if ( !v30 )
        {
          v18 = -1073738821;
          goto LABEL_121;
        }
        if ( (*(_BYTE *)a2 & 0x20) == 0 )
          goto LABEL_68;
        v31 = *((_DWORD *)a2 + 19);
        if ( v31 )
        {
          switch ( v31 )
          {
            case 1:
              LODWORD(ExtCount) = *((_DWORD *)a2 + 20);
              StringCchPrintfW(v30, v5, L"%s%s%s%s%s%06d", v53, v7, v51, v6, v52, ExtCount);
              goto LABEL_69;
            case 2:
              v39 = SystemTime;
              v57 = SystemTime;
              DayOfYear = PlaiGetDayOfYear(&v57);
              LODWORD(ExtCount) = (unsigned __int16)_mm_cvtsi128_si32((__m128i)v39);
              StringCchPrintfW(v30, v5, L"%s%s%s%s%s%04d%03d", v53, v7, v51, v6, v52, ExtCount, DayOfYear);
              goto LABEL_69;
            case 3:
              LODWORD(ExtCount) = SystemTime.wYear;
              StringCchPrintfW(v30, v5, L"%s%s%s%s%s%04d%02d", v53, v7, v51, v6, v52, ExtCount, SystemTime.wMonth);
              goto LABEL_69;
          }
          if ( v31 != 4 )
          {
            if ( v31 == 5 )
            {
              LODWORD(ExtCount) = SystemTime.wYear;
              StringCchPrintfW(
                v30,
                v5,
                L"%s%s%s%s%s%04d%02d%02d%02d",
                v53,
                v7,
                v51,
                v6,
                v52,
                ExtCount,
                SystemTime.wMonth,
                SystemTime.wDay,
                SystemTime.wHour);
              goto LABEL_69;
            }
            if ( v31 == 6 )
            {
              LODWORD(ExtCount) = SystemTime.wMonth;
              StringCchPrintfW(
                v30,
                v5,
                L"%s%s%s%s%s%02d%02d%02d%02d",
                v53,
                v7,
                v51,
                v6,
                v52,
                ExtCount,
                SystemTime.wDay,
                SystemTime.wHour,
                SystemTime.wMinute);
              goto LABEL_69;
            }
            if ( v31 != -1 )
            {
LABEL_69:
              v32 = a1;
              if ( (*(_DWORD *)a2 & 0x1000) != 0 )
              {
                if ( *((_DWORD *)a2 + 35) )
                {
                  v32 = a1 | 1;
                  if ( !*((_DWORD *)a2 + 44) )
                    *((_DWORD *)a2 + 44) = 1;
                }
              }
              v33 = 128;
              if ( (v32 & 1) != 0 )
              {
                if ( (v32 & 2) != 0 )
                {
                  v34 = L"_%03d";
                }
                else if ( (v32 & 4) != 0 )
                {
                  v34 = L"_xxx";
                }
                else
                {
                  StringCchPrintfW(v59, 0x80u, L"_%03d", *((unsigned int *)a2 + 44));
                  v34 = v59;
                }
                StringCchCatW(v30, v5, v34);
              }
              if ( (*(_BYTE *)a2 & 2) != 0 )
              {
                if ( *((_WORD *)a2 + 36) )
                {
                  if ( *((_WORD *)a2 + 36) == 1 )
                  {
                    v40 = L".tsv";
                  }
                  else if ( *((_WORD *)a2 + 36) == 2 || *((_WORD *)a2 + 36) == 3 )
                  {
                    v40 = L".blg";
                  }
                  else
                  {
                    if ( (unsigned int)*((unsigned __int16 *)a2 + 36) - 4 > 1 )
                      goto LABEL_99;
                    v40 = L".etl";
                  }
                }
                else
                {
                  v40 = L".csv";
                }
                StringCchCatW(v30, v5, v40);
              }
LABEL_99:
              if ( (v32 & 0x20) != 0 )
              {
                v45 = -1;
                do
                  ++v45;
                while ( v30[v45] );
                LODWORD(v5) = v45 + 1;
                if ( !a4 || (unsigned int)v5 > *a3 )
                {
                  v18 = -1073738814;
                  goto LABEL_120;
                }
                StringCchCopyW(a4, *a3, v30);
                v41 = v46;
              }
              else
              {
                if ( a4 )
                  v33 = *a3;
                v41 = v59;
                v18 = -1073738814;
                if ( a4 )
                  v41 = a4;
                v42 = -1073738814;
                if ( a4 )
                  v42 = 0;
                v43 = ExpandEnvironmentStringsW(v30, v41, v33);
                if ( v43 )
                {
                  LODWORD(v5) = v43;
                  if ( !a4 || *a3 >= v43 )
                    v18 = v42;
                }
                else
                {
                  LastError = GetLastError();
                  v18 = PlaliErrorToPdhStatus(LastError);
                }
                if ( v18 )
                  goto LABEL_120;
              }
              v18 = PlaliScanForInvalidChar(v41);
LABEL_120:
              v47 = GetProcessHeap();
              HeapFree(v47, 0, v30);
              goto LABEL_121;
            }
LABEL_68:
            StringCchPrintfW(v30, v5, L"%s%s%s%s", v53, v7, v51, v6);
            goto LABEL_69;
          }
          wDay = SystemTime.wDay;
          v36 = L"%s%s%s%s%s%04d%02d%02d";
          wMonth = SystemTime.wMonth;
          wYear = SystemTime.wYear;
        }
        else
        {
          wDay = SystemTime.wHour;
          v36 = L"%s%s%s%s%s%02d%02d%02d";
          wMonth = SystemTime.wDay;
          wYear = SystemTime.wMonth;
        }
        LODWORD(ExtCount) = wYear;
        StringCchPrintfW(v30, v5, v36, v53, v7, v51, v6, v52, ExtCount, wMonth, wDay);
        goto LABEL_69;
      }
    }
    else
    {
      StringCchCopyW(v62, 0x104u, Filename);
      v6 = v62;
    }
LABEL_48:
    v24 = -1;
    do
      ++v24;
    while ( v6[v24] );
    v25 = 2 * v24;
    goto LABEL_52;
  }
  if ( (*(_DWORD *)a2 & 0x8000) == 0
    || (v7 = (const unsigned __int16 *)*((_QWORD *)a2 + 8), (unsigned int)PlaliIsStringEmpty(v7)) )
  {
    v7 = v6;
  }
  if ( !(unsigned int)PlaliIsStringEmpty(v7) )
  {
    v10 = v9;
    v51 = L"!";
    v11 = v9;
    v12 = wcsstr(v8, L"!");
    IsStringEmpty = PlaliIsStringEmpty(v12);
    v15 = -1;
    if ( !IsStringEmpty )
    {
      v10 = 1;
      do
        ++v15;
      while ( *(_WORD *)(v14 + 2 * v15) );
      if ( v15 > 1 )
        v11 = 1;
    }
    if ( *((_DWORD *)a2 + 19) != -1 )
    {
      v16 = (const unsigned __int16 *)&szPassword;
      if ( v11 )
        v16 = L"_";
      v52 = v16;
      goto LABEL_20;
    }
    if ( v11 )
    {
LABEL_20:
      v6 = (unsigned __int16 *)&szPassword;
      if ( v11 || v10 )
        v51 = (const unsigned __int16 *)&szPassword;
      v17 = L"SQL:";
      if ( CompareStringW(0x7Fu, 1u, v7, 4, L"SQL:", 4) != 2 )
        v17 = (const wchar_t *)&szPassword;
      v53 = (const size_t *)v17;
      goto LABEL_48;
    }
  }
LABEL_27:
  v18 = -1073738819;
LABEL_121:
  *a3 = v5;
  return v18;
}

```

## disassembly

```asm
0x1801303ec  mov     [rsp-8+arg_0], rbx
0x1801303f1  push    rbp
0x1801303f2  push    rsi
0x1801303f3  push    rdi
0x1801303f4  push    r12
0x1801303f6  push    r13
0x1801303f8  push    r14
0x1801303fa  push    r15
0x1801303fc  lea     rbp, [rsp-6D0h]
0x180130404  sub     rsp, 7D0h
0x18013040b  mov     rax, cs:__security_cookie
0x180130412  xor     rax, rsp
0x180130415  mov     [rbp+700h+var_40], rax
0x18013041c  mov     [rsp+800h+var_788], ecx
0x180130420  xorps   xmm0, xmm0
0x180130423  lea     rcx, [rbp+700h+SystemTime]; lpSystemTime
0x180130427  mov     [rbp+700h+lpDst], r9
0x18013042b  movups  xmmword ptr [rbp+700h+SystemTime.wYear], xmm0
0x18013042f  mov     [rbp+700h+var_780], r8
0x180130433  mov     r15, rdx
0x180130436  call    cs:__imp_GetLocalTime
0x18013043c  xor     r8d, r8d
0x18013043f  lea     rax, asc_180152070; "_"
0x180130446  test    byte ptr [r15], 10h
0x18013044a  mov     r13d, r8d
0x18013044d  mov     [rsp+800h+var_798], rax
0x180130452  mov     r12d, r8d
0x180130455  mov     r14d, r8d
0x180130458  jz      short loc_18013045E
0x18013045a  mov     r12, [r15+38h]
0x18013045e  test    dword ptr [r15], 2000h
0x180130465  jz      short loc_18013046B
0x180130467  mov     r14, [r15+30h]
0x18013046b  test    byte ptr [r15], 2
0x18013046f  mov     ebx, 1
0x180130474  jz      loc_180130572
0x18013047a  cmp     dword ptr [r15+48h], 6
0x18013047f  jnz     loc_180130572
0x180130485  test    dword ptr [r15], 8000h
0x18013048c  jz      short loc_18013049E
0x18013048e  mov     r14, [r15+40h]
0x180130492  mov     rcx, r14; unsigned __int16 *
0x180130495  call    ?PlaliIsStringEmpty@@YAHPEBG@Z; PlaliIsStringEmpty(ushort const *)
0x18013049a  test    eax, eax
0x18013049c  jz      short loc_1801304A1
0x18013049e  mov     r14, r12
0x1801304a1  mov     rcx, r14; unsigned __int16 *
0x1801304a4  call    ?PlaliIsStringEmpty@@YAHPEBG@Z; PlaliIsStringEmpty(ushort const *)
0x1801304a9  test    eax, eax
0x1801304ab  jnz     loc_180130568
0x1801304b1  lea     rax, SubStr; "!"
0x1801304b8  mov     esi, r8d
0x1801304bb  mov     rdx, rax; SubStr
0x1801304be  mov     [rsp+800h+var_7A0], rax
0x1801304c3  mov     edi, r8d
0x1801304c6  call    cs:__imp_wcsstr
0x1801304cc  mov     rcx, rax; unsigned __int16 *
0x1801304cf  mov     r8, rax
0x1801304d2  call    ?PlaliIsStringEmpty@@YAHPEBG@Z; PlaliIsStringEmpty(ushort const *)
0x1801304d7  xor     edx, edx
0x1801304d9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1801304dd  test    eax, eax
0x1801304df  jnz     short loc_1801304F3
0x1801304e1  mov     esi, ebx
0x1801304e3  inc     rcx
0x1801304e6  cmp     [r8+rcx*2], dx
0x1801304eb  jnz     short loc_1801304E3
0x1801304ed  cmp     rcx, rbx
0x1801304f0  cmova   edi, ebx
0x1801304f3  cmp     dword ptr [r15+4Ch], 0FFFFFFFFh
0x1801304f8  lea     rbx, szPassword
0x1801304ff  jz      short loc_180130564
0x180130501  test    edi, edi
0x180130503  lea     rax, asc_180152070; "_"
0x18013050a  mov     rcx, rbx
0x18013050d  cmovnz  rcx, rax
0x180130511  mov     [rsp+800h+var_798], rcx
0x180130516  mov     r12, rbx
0x180130519  test    edi, edi
0x18013051b  jnz     short loc_180130521
0x18013051d  test    esi, esi
0x18013051f  jz      short loc_180130526
0x180130521  mov     [rsp+800h+var_7A0], rbx
0x180130526  mov     eax, 4
0x18013052b  lea     rdi, aSql; "SQL:"
0x180130532  mov     [rsp+800h+cchCount2], eax; cchCount2
0x180130536  mov     r9d, eax; cchCount1
0x180130539  mov     r8, r14; lpString1
0x18013053c  mov     [rsp+800h+lpString2], rdi; lpString2
0x180130541  lea     edx, [rax-3]; dwCmpFlags
0x180130544  lea     ecx, [rax+7Bh]; Locale
0x180130547  call    cs:__imp_CompareStringW
0x18013054d  cmp     eax, 2
0x180130550  cmovnz  rdi, rbx
0x180130554  mov     [rsp+800h+var_790], rdi
0x180130559  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18013055d  xor     ebx, ebx
0x18013055f  jmp     loc_1801306BE
0x180130564  test    edi, edi
0x180130566  jnz     short loc_180130516
0x180130568  mov     ebx, 0C0000BBDh
0x18013056d  jmp     loc_180130AED
0x180130572  lea     rsi, asc_180150280; "\\"
0x180130579  mov     rcx, r14; unsigned __int16 *
0x18013057c  mov     [rsp+800h+var_7A0], rsi
0x180130581  call    ?PlaliIsStringEmpty@@YAHPEBG@Z; PlaliIsStringEmpty(ushort const *)
0x180130586  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18013058a  lea     rbx, szPassword
0x180130591  test    eax, eax
0x180130593  jz      short loc_18013059E
0x180130595  lea     r14, aSystemdrivePer_0; "%SystemDrive%\\PerfLogs"
0x18013059c  jmp     short loc_1801305BE
0x18013059e  mov     rcx, rdi
0x1801305a1  inc     rcx
0x1801305a4  cmp     [r14+rcx*2], r8w
0x1801305a9  jnz     short loc_1801305A1
0x1801305ab  cmp     word ptr [r14+rcx*2-2], 5Ch ; '\'
0x1801305b2  mov     rax, rbx
0x1801305b5  cmovnz  rax, rsi
0x1801305b9  mov     [rsp+800h+var_7A0], rax
0x1801305be  mov     rcx, r12; unsigned __int16 *
0x1801305c1  call    ?PlaliIsStringEmpty@@YAHPEBG@Z; PlaliIsStringEmpty(ushort const *)
0x1801305c6  test    eax, eax
0x1801305c8  jz      short loc_1801305DF
0x1801305ca  test    byte ptr [r15], 20h
0x1801305ce  jz      short loc_1801305D7
0x1801305d0  cmp     dword ptr [r15+4Ch], 0FFFFFFFFh
0x1801305d5  jz      short loc_180130568
0x1801305d7  mov     r12, rbx
0x1801305da  mov     [rsp+800h+var_798], rbx
0x1801305df  mov     ecx, 100h
0x1801305e4  mov     [rsp+800h+var_790], rbx
0x1801305e9  mov     [rsp+800h+ExtCount], rcx; ExtCount
0x1801305ee  lea     rax, [rbp+700h+String1]
0x1801305f5  mov     [rsp+800h+Ext], rax; Ext
0x1801305fa  xor     r9d, r9d; Dir
0x1801305fd  mov     [rsp+800h+FilenameCount], rcx; FilenameCount
0x180130602  lea     rax, [rbp+700h+Filename]
0x180130609  mov     qword ptr [rsp+800h+cchCount2], rax; Filename
0x18013060e  xor     edx, edx; Drive
0x180130610  mov     rcx, r12; FullPath
0x180130613  mov     [rsp+800h+lpString2], r8; DirCount
0x180130618  call    cs:__imp__wsplitpath_s
0x18013061e  lea     rdx, aEtl; ".etl"
0x180130625  lea     rcx, [rbp+700h+String1]; String1
0x18013062c  call    cs:__imp__wcsicmp
0x180130632  xor     ebx, ebx
0x180130634  test    eax, eax
0x180130636  jz      short loc_180130680
0x180130638  lea     rdx, aBlg; ".blg"
0x18013063f  lea     rcx, [rbp+700h+String1]; String1
0x180130646  call    cs:__imp__wcsicmp
0x18013064c  test    eax, eax
0x18013064e  jz      short loc_180130680
0x180130650  lea     rdx, aCsv; ".csv"
0x180130657  lea     rcx, [rbp+700h+String1]; String1
0x18013065e  call    cs:__imp__wcsicmp
0x180130664  test    eax, eax
0x180130666  jz      short loc_180130680
0x180130668  lea     rdx, aTsv; ".tsv"
0x18013066f  lea     rcx, [rbp+700h+String1]; String1
0x180130676  call    cs:__imp__wcsicmp
0x18013067c  test    eax, eax
0x18013067e  jnz     short loc_1801306B9
0x180130680  lea     rcx, [rbp+700h+Filename]
0x180130687  mov     rax, rdi
0x18013068a  inc     rax
0x18013068d  cmp     [rcx+rax*2], bx
0x180130691  jnz     short loc_18013068A
0x180130693  mov     edx, 104h; unsigned __int64
0x180130698  cmp     rax, rdx
0x18013069b  jnb     short loc_1801306B9
0x18013069d  lea     r8, [rbp+700h+Filename]; unsigned __int16 *
0x1801306a4  lea     rcx, [rbp+700h+var_250]; unsigned __int16 *
0x1801306ab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801306b0  lea     r12, [rbp+700h+var_250]
0x1801306b7  jmp     short loc_1801306BE
0x1801306b9  test    r12, r12
0x1801306bc  jz      short loc_1801306CF
0x1801306be  mov     rax, rdi
0x1801306c1  inc     rax
0x1801306c4  cmp     [r12+rax*2], bx
0x1801306c9  jnz     short loc_1801306C1
0x1801306cb  add     eax, eax
0x1801306cd  jmp     short loc_1801306D1
0x1801306cf  mov     eax, ebx
0x1801306d1  shr     eax, 1
0x1801306d3  mov     ecx, eax
0x1801306d5  test    r14, r14
0x1801306d8  jz      short loc_1801306EB
0x1801306da  mov     rax, rdi
0x1801306dd  inc     rax
0x1801306e0  cmp     [r14+rax*2], bx
0x1801306e5  jnz     short loc_1801306DD
0x1801306e7  add     eax, eax
0x1801306e9  jmp     short loc_1801306ED
0x1801306eb  mov     eax, ebx
0x1801306ed  shr     eax, 1
0x1801306ef  lea     r13d, [rax+20h]
0x1801306f3  add     r13d, ecx
0x1801306f6  mov     esi, r13d
0x1801306f9  lea     rbx, ds:0[r13*2]
0x180130701  call    cs:__imp_GetProcessHeap
0x180130707  mov     r8, rbx; dwBytes
0x18013070a  mov     edx, 8; dwFlags
0x18013070f  mov     rcx, rax; hHeap
0x180130712  call    cs:__imp_HeapAlloc
0x180130718  mov     rdi, rax
0x18013071b  test    rax, rax
0x18013071e  jnz     short loc_18013072A
0x180130720  mov     ebx, 0C0000BBBh
0x180130725  jmp     loc_180130AED
0x18013072a  test    byte ptr [r15], 20h
0x18013072e  jz      short loc_180130777
0x180130730  mov     eax, [r15+4Ch]
0x180130734  test    eax, eax
0x180130736  jz      loc_180130984
0x18013073c  cmp     eax, 1
0x18013073f  jz      loc_180130942
0x180130745  cmp     eax, 2
0x180130748  jz      loc_1801308E7
0x18013074e  cmp     eax, 3
0x180130751  jz      loc_1801308CE
0x180130757  cmp     eax, 4
0x18013075a  jz      loc_18013087C
0x180130760  cmp     eax, 5
0x180130763  jz      loc_180130820
0x180130769  cmp     eax, 6
0x18013076c  jz      loc_1801307F5
0x180130772  cmp     eax, 0FFFFFFFFh
0x180130775  jnz     short loc_1801307A2
0x180130777  mov     rax, [rsp+800h+var_7A0]
0x18013077c  lea     r8, aSSSS; "%s%s%s%s"
0x180130783  mov     r9, [rsp+800h+var_790]
0x180130788  mov     rdx, rsi; unsigned __int64
0x18013078b  mov     [rsp+800h+FilenameCount], r12
0x180130790  mov     rcx, rdi; unsigned __int16 *
0x180130793  mov     qword ptr [rsp+800h+cchCount2], rax
0x180130798  mov     [rsp+800h+lpString2], r14
0x18013079d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801307a2  test    dword ptr [r15], 1000h
0x1801307a9  mov     ebx, [rsp+800h+var_788]
0x1801307ad  jz      short loc_1801307D1
0x1801307af  cmp     dword ptr [r15+8Ch], 0
0x1801307b7  jz      short loc_1801307D1
0x1801307b9  or      ebx, 1
0x1801307bc  cmp     dword ptr [r15+0B0h], 0
0x1801307c4  jnz     short loc_1801307D1
0x1801307c6  mov     dword ptr [r15+0B0h], 1
0x1801307d1  mov     r12d, 80h
0x1801307d7  test    bl, 1
0x1801307da  jz      loc_1801309D3
0x1801307e0  test    bl, 2
0x1801307e3  jz      loc_18013099C
0x1801307e9  lea     r8, a03d; "_%03d"
0x1801307f0  jmp     loc_1801309C8
0x1801307f5  movzx   r8d, [rbp+700h+SystemTime.wMonth]
0x1801307fa  movzx   eax, [rbp+700h+SystemTime.wMinute]
0x1801307fe  movzx   ecx, [rbp+700h+SystemTime.wHour]
0x180130802  movzx   edx, [rbp+700h+SystemTime.wDay]
0x180130806  mov     [rsp+800h+var_7A8], eax
0x18013080a  mov     [rsp+800h+var_7B0], ecx
0x18013080e  mov     [rsp+800h+var_7B8], edx
0x180130812  mov     dword ptr [rsp+800h+ExtCount], r8d
0x180130817  lea     r8, aSSSSS02d02d02d_0; "%s%s%s%s%s%02d%02d%02d%02d"
0x18013081e  jmp     short loc_180130849
0x180130820  movzx   r8d, [rbp+700h+SystemTime.wYear]
0x180130825  movzx   eax, [rbp+700h+SystemTime.wHour]
0x180130829  movzx   ecx, [rbp+700h+SystemTime.wDay]
0x18013082d  movzx   edx, [rbp+700h+SystemTime.wMonth]
0x180130831  mov     [rsp+800h+var_7A8], eax
0x180130835  mov     [rsp+800h+var_7B0], ecx
0x180130839  mov     [rsp+800h+var_7B8], edx
0x18013083d  mov     dword ptr [rsp+800h+ExtCount], r8d
0x180130842  lea     r8, aSSSSS04d02d02d; "%s%s%s%s%s%04d%02d%02d%02d"
0x180130849  mov     rax, [rsp+800h+var_798]
0x18013084e  mov     rdx, rsi; unsigned __int64
0x180130851  mov     r9, [rsp+800h+var_790]
0x180130856  mov     rcx, rdi; unsigned __int16 *
0x180130859  mov     [rsp+800h+Ext], rax
0x18013085e  mov     rax, [rsp+800h+var_7A0]
0x180130863  mov     [rsp+800h+FilenameCount], r12
0x180130868  mov     qword ptr [rsp+800h+cchCount2], rax
0x18013086d  mov     [rsp+800h+lpString2], r14
0x180130872  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180130877  jmp     loc_1801307A2
0x18013087c  movzx   eax, [rbp+700h+SystemTime.wDay]
0x180130880  lea     r8, aSSSSS04d02d02d_0; "%s%s%s%s%s%04d%02d%02d"
0x180130887  movzx   ecx, [rbp+700h+SystemTime.wMonth]
0x18013088b  movzx   edx, [rbp+700h+SystemTime.wYear]
0x18013088f  mov     r9, [rsp+800h+var_790]
0x180130894  mov     [rsp+800h+var_7B0], eax
0x180130898  mov     rax, [rsp+800h+var_798]
0x18013089d  mov     [rsp+800h+var_7B8], ecx
0x1801308a1  mov     rcx, rdi; unsigned __int16 *
0x1801308a4  mov     dword ptr [rsp+800h+ExtCount], edx
0x1801308a8  mov     rdx, rsi; unsigned __int64
0x1801308ab  mov     [rsp+800h+Ext], rax
0x1801308b0  mov     rax, [rsp+800h+var_7A0]
0x1801308b5  mov     [rsp+800h+FilenameCount], r12
  ... truncated ...
```
