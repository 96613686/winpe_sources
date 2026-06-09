# CheckFileCopyOptions(_INIENVIRONMENT *,_INIVERSION *,_INIDRIVER *,_INTERNAL_DRV_FILE *,ulong,ulong,int *,int *)

- ea: `0x18006a41c`
- end: `0x18006aa19`
- name: `?CheckFileCopyOptions@@YAHPEAU_INIENVIRONMENT@@PEAU_INIVERSION@@PEAU_INIDRIVER@@PEAU_INTERNAL_DRV_FILE@@KKPEAH4@Z`
- size: `1533`
- prototype: `__int64 __usercall@<rax>(struct _INIENVIRONMENT *@<rcx>, struct _INIVERSION *@<rdx>, struct _INIDRIVER *@<r8>, struct _INTERNAL_DRV_FILE *@<r9>, unsigned int, unsigned int, int *, int *)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180069484`
- `0x1800705a0`

## callees

- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x18000b9ec`
- `0x18000c380`
- `0x18000d474`
- `0x18000edc4`
- `0x180013c90`
- `0x18003e984`
- `0x180040a14`
- `0x180042964`
- `0x180042ad0`
- `0x180046650`
- `0x180047330`
- `0x18006a41c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006a533`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006a533`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006a51b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006a6ab`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006a51b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006a6ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a9d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a9d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a4ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a946`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a953`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a4ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a946`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a953`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006a689`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006a73d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006a76d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006a689`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006a73d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006a76d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18006a829`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18006a829`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18006a69c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18006a7c2`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18006a69c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18006a7c2`
- `SPOOLSS!DllFreeSplMem` at `0x18006a99e`
- `SPOOLSS!DllFreeSplMem` at `0x18006a9ac`
- `SPOOLSS!DllFreeSplMem` at `0x18006a9bc`
- `SPOOLSS!DllFreeSplMem` at `0x18006a9cc`
- `SPOOLSS!DllFreeSplMem` at `0x18006a99e`
- `SPOOLSS!DllFreeSplMem` at `0x18006a9ac`
- `SPOOLSS!DllFreeSplMem` at `0x18006a9bc`
- `SPOOLSS!DllFreeSplMem` at `0x18006a9cc`
- `SPOOLSS!DllAllocSplMem` at `0x18006a54b`
- `SPOOLSS!DllAllocSplMem` at `0x18006a560`
- `SPOOLSS!DllAllocSplMem` at `0x18006a54b`
- `SPOOLSS!DllAllocSplMem` at `0x18006a560`

## string_xrefs

- `0x18006a4f7`: `CheckFileCopyOptions`
- `0x18006a6f9`: `CheckFileCopyOptions`
- `0x18006a798`: `CheckFileCopyOptions`
- `0x18006a84b`: `CheckFileCopyOptions`
- `0x18006a86d`: `CheckFileCopyOptions`
- `0x18006a8a4`: `CheckFileCopyOptions`
- `0x18006a915`: `CheckFileCopyOptions`
- `0x18006a935`: `CheckFileCopyOptions`
- `0x18006a96f`: `CheckFileCopyOptions`
- `0x18006a9e7`: `CheckFileCopyOptions`
- `0x18006a6f2`: `Copying all files, not doing version checking`
- `0x18006a507`: `Only copying newer driver files`
- `0x18006a90e`: `APD_COPY_NEW_FILES is specified, and the main driver files are different. The existing driver will be used.`
- `0x18006a968`: `The files on the source are newer than the files on the target, update needed.`
- `0x18006a905`: `Didn't find any newer files, skipping installation.`

## pseudocode

```c
__int64 __fastcall CheckFileCopyOptions(
        struct _INIENVIRONMENT *a1,
        struct _INIVERSION *a2,
        struct _INIDRIVER *a3,
        const wchar_t **a4,
        unsigned int a5,
        unsigned int a6,
        int *a7,
        int *a8)
{
  int *v9; // rsi
  unsigned int v11; // r12d
  wchar_t *v13; // rax
  __int64 v14; // rdx
  unsigned __int16 *v15; // r15
  int v16; // r9d
  unsigned __int16 *v17; // r13
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  char *v21; // rax
  char *v22; // r8
  __int64 v23; // rcx
  int v24; // edx
  unsigned int v25; // eax
  int v26; // edi
  unsigned int v27; // r14d
  const wchar_t **v28; // rdi
  __int64 v29; // rsi
  HANDLE FirstFileW; // rax
  wchar_t *v31; // rax
  wchar_t *v32; // rdi
  unsigned __int16 *v33; // r9
  HANDLE v34; // rax
  __int64 v35; // rcx
  LONG v36; // eax
  DWORD LastError; // eax
  int v39; // [rsp+30h] [rbp-D0h]
  int v40; // [rsp+34h] [rbp-CCh]
  unsigned int v41; // [rsp+38h] [rbp-C8h] BYREF
  int v42; // [rsp+3Ch] [rbp-C4h]
  unsigned __int16 *v43; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t **v44; // [rsp+48h] [rbp-B8h]
  __int64 v45; // [rsp+50h] [rbp-B0h] BYREF
  struct _INIVERSION *v46; // [rsp+58h] [rbp-A8h]
  int *v47; // [rsp+60h] [rbp-A0h]
  int *v48; // [rsp+68h] [rbp-98h]
  struct _WIN32_FIND_DATAW v49; // [rsp+70h] [rbp-90h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+2C0h] [rbp+1C0h] BYREF

  v9 = a8;
  v46 = a2;
  v11 = 0;
  v44 = a4;
  v47 = a7;
  v48 = a8;
  v43 = 0;
  v45 = 0;
  memset_0(&v49, 0, sizeof(v49));
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v41 = 0;
  if ( !a7 )
  {
LABEL_94:
    LastError = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceInfo("CheckFileCopyOptions", L"Failing call.  Error %d", LastError);
    return v11;
  }
  v40 = 0;
  if ( a8 )
    *a8 = 0;
  *a7 = 0;
  if ( a6 != 1 && a6 != 2 )
  {
    if ( a6 == 4 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceInfo("CheckFileCopyOptions", L"Copying all files, not doing version checking");
    }
    else
    {
      if ( a6 != 8 )
      {
        SetLastError(0x57u);
        goto LABEL_89;
      }
      if ( a3 )
      {
        LocalSpoolerTelemetry::WriteDbgTraceInfo("CheckFileCopyOptions", L"Only copying newer driver files");
        v13 = wcsrchr(*a4, 0x5Cu);
        if ( v13 )
        {
          v14 = *((_QWORD *)a3 + 4);
          if ( v14 )
          {
            if ( !(unsigned int)_o__wcsicmp(v13 + 1, v14) )
              v40 = 1;
          }
        }
        goto LABEL_14;
      }
      LocalSpoolerTelemetry::WriteDbgTraceInfo(
        "CheckFileCopyOptions",
        L"This is not an upgrade, not doing version checking");
    }
    v11 = 1;
    goto LABEL_89;
  }
LABEL_14:
  v15 = (unsigned __int16 *)DllAllocSplMem(1034);
  if ( !v15 )
    goto LABEL_89;
  v17 = (unsigned __int16 *)DllAllocSplMem(1034);
  if ( !v17 )
    goto LABEL_87;
  if ( !GetEnvironmentScratchDirectory(v15, 0x104u, a1, v16) )
    goto LABEL_87;
  v18 = StringCchCatW(v15, 0x205u, L"\\");
  if ( !(unsigned int)BoolFromHResult(v18) )
    goto LABEL_87;
  v19 = StringCchCatW(v15, 0x205u, *((const unsigned __int16 **)v46 + 3));
  if ( !(unsigned int)BoolFromHResult(v19) )
    goto LABEL_87;
  v20 = StrCatAlloc(&v45, v15, L"\\New", 0);
  if ( !(unsigned int)BoolFromStatus(v20) )
    goto LABEL_87;
  v21 = (char *)*((_QWORD *)a1 + 3);
  v22 = (char *)((char *)L"Windows 4.0" - v21);
  do
  {
    v23 = *(unsigned __int16 *)&v22[(_QWORD)v21];
    v24 = *(unsigned __int16 *)v21 - (_DWORD)v23;
    if ( v24 )
      break;
    v21 += 2;
  }
  while ( (_DWORD)v23 );
  if ( !v24 )
  {
    v25 = StrCatAlloc(&v43, v15, L"\\Color", 0);
    if ( !(unsigned int)BoolFromStatus(v25) )
      goto LABEL_87;
  }
  v26 = 0;
  v39 = 0;
  v42 = 0;
  if ( a3 )
    SafeIncrementReference((unsigned int *)a3 + 4);
  LeaveSplSem(v23);
  v27 = 0;
  if ( a5 )
  {
    while ( 1 )
    {
      v28 = v44;
      v29 = 4LL * v27;
      FirstFileW = FindFirstFileW(v44[v29], &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
        goto LABEL_84;
      FindClose(FirstFileW);
      v31 = wcsrchr(v28[v29], 0x5Cu);
      if ( !v31 )
        goto LABEL_84;
      v32 = v31 + 1;
      if ( v43 && (unsigned int)IsAColorFile(v44[v29]) )
      {
        v33 = v43;
      }
      else
      {
        if ( !v27 && !v40 && a3 )
          v32 = (wchar_t *)*((_QWORD *)a3 + 4);
        StringCchPrintfW(v17, 0x205u, L"%ws\\%ws", v45, v32);
        v34 = FindFirstFileW(v17, &v49);
        if ( v34 != (HANDLE)-1LL )
          goto LABEL_49;
        v33 = v15;
      }
      StringCchPrintfW(v17, 0x205u, L"%ws\\%ws", v33, v32);
      v34 = FindFirstFileW(v17, &v49);
      if ( v34 == (HANDLE)-1LL )
      {
        if ( v27 || v40 || !a3 )
        {
          v42 = 1;
          goto LABEL_67;
        }
        LocalSpoolerTelemetry::WriteDbgTraceInfo(
          "CheckFileCopyOptions",
          L"Didn't find %ws on the target, treating it as a newer source file.",
          FindFileData.cFileName);
        goto LABEL_47;
      }
LABEL_49:
      FindClose(v34);
      EnterSplSem(0);
      if ( a3 && *((_DWORD *)a3 + 4) )
        SafeDecrementReference((unsigned int *)a3 + 4);
      if ( !GetDriverFileCachedVersion(v46, v17, &v41) )
      {
        SetLastError(0x3EBu);
        goto LABEL_87;
      }
      if ( a3 )
        SafeIncrementReference((unsigned int *)a3 + 4);
      LeaveSplSem(v35);
      if ( LODWORD(v44[v29 + 1]) == v41 )
      {
        v36 = CompareFileTime(&FindFileData.ftLastWriteTime, &v49.ftLastWriteTime);
        if ( v36 != 1 )
        {
          if ( v36 == -1 )
          {
LABEL_62:
            LocalSpoolerTelemetry::WriteDbgTraceInfo(
              "CheckFileCopyOptions",
              L"Target %ws is newer than %ws",
              v49.cFileName,
              FindFileData.cFileName);
            if ( a6 == 1 )
            {
              LocalSpoolerTelemetry::WriteDbgTraceInfo(
                "CheckFileCopyOptions",
                L"There is a newer target file, so the driver cannot be upgraded.");
              goto LABEL_78;
            }
            if ( a6 == 8 && !v27 && !v40 && a3 )
            {
              LocalSpoolerTelemetry::WriteDbgTraceInfo(
                "CheckFileCopyOptions",
                L"APD_COPY_NEW_FILES is specified, and the main driver files are different. The existing driver will be used.");
              goto LABEL_76;
            }
          }
          else
          {
            LocalSpoolerTelemetry::WriteDbgTraceInfo(
              "CheckFileCopyOptions",
              L"Target %ws is the same as %ws",
              v49.cFileName,
              FindFileData.cFileName);
          }
LABEL_67:
          v26 = v39;
          goto LABEL_68;
        }
      }
      else if ( LODWORD(v44[v29 + 1]) <= v41 )
      {
        goto LABEL_62;
      }
      LocalSpoolerTelemetry::WriteDbgTraceInfo(
        "CheckFileCopyOptions",
        L"Source %ws is newer than %ws",
        FindFileData.cFileName,
        v49.cFileName);
      if ( a6 == 2 )
      {
        LocalSpoolerTelemetry::WriteDbgTraceInfo(
          "CheckFileCopyOptions",
          L"There is a newer source file, so the driver cannot be downgraded.");
LABEL_78:
        SetLastError(0x3EBu);
        goto LABEL_84;
      }
LABEL_47:
      v26 = 1;
      v39 = 1;
LABEL_68:
      if ( ++v27 >= a5 )
      {
        v9 = v48;
        break;
      }
    }
  }
  if ( a6 != 8 || v26 || !a3 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceInfo(
      "CheckFileCopyOptions",
      L"The files on the source are newer than the files on the target, update needed.");
LABEL_83:
    v11 = 1;
    goto LABEL_84;
  }
  if ( v42 )
  {
    if ( v9 )
      *v9 = 1;
    goto LABEL_83;
  }
  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "CheckFileCopyOptions",
    L"Didn't find any newer files, skipping installation.");
LABEL_76:
  *v47 = 1;
LABEL_84:
  EnterSplSem(0);
  if ( a3 && *((_DWORD *)a3 + 4) )
    SafeDecrementReference((unsigned int *)a3 + 4);
LABEL_87:
  DllFreeSplMem(v15);
  if ( v17 )
    DllFreeSplMem(v17);
LABEL_89:
  if ( v43 )
    DllFreeSplMem(v43);
  if ( v45 )
    DllFreeSplMem(v45);
  if ( !v11 )
    goto LABEL_94;
  return v11;
}

```

## disassembly

```asm
0x18006a41c  push    rbp
0x18006a41e  push    rbx
0x18006a41f  push    rsi
0x18006a420  push    rdi
0x18006a421  push    r12
0x18006a423  push    r13
0x18006a425  push    r14
0x18006a427  push    r15
0x18006a429  lea     rbp, [rsp-428h]
0x18006a431  sub     rsp, 528h
0x18006a438  mov     rax, cs:__security_cookie
0x18006a43f  xor     rax, rsp
0x18006a442  mov     [rbp+460h+var_50], rax
0x18006a449  mov     r14, [rbp+460h+arg_30]
0x18006a450  mov     rbx, r8
0x18006a453  mov     rsi, [rbp+460h+arg_38]
0x18006a45a  mov     rdi, rcx
0x18006a45d  mov     [rsp+560h+var_508], rdx
0x18006a462  lea     rcx, [rsp+560h+var_4F0]; void *
0x18006a467  xor     r12d, r12d
0x18006a46a  mov     [rsp+560h+var_518], r9
0x18006a46f  mov     r13d, 250h
0x18006a475  mov     [rsp+560h+var_500], r14
0x18006a47a  mov     r8d, r13d; Size
0x18006a47d  mov     [rsp+560h+var_4F8], rsi
0x18006a482  xor     edx, edx; Val
0x18006a484  mov     [rsp+560h+var_520], r12
0x18006a489  mov     r15, r9
0x18006a48c  mov     [rsp+560h+var_510], r12
0x18006a491  call    memset_0
0x18006a496  mov     r8d, r13d; Size
0x18006a499  lea     rcx, [rbp+460h+FindFileData]; void *
0x18006a4a0  xor     edx, edx; Val
0x18006a4a2  call    memset_0
0x18006a4a7  xor     eax, eax
0x18006a4a9  mov     [rsp+560h+var_528], eax
0x18006a4ad  test    r14, r14
0x18006a4b0  jz      loc_18006A9D7
0x18006a4b6  mov     [rsp+560h+var_52C], eax
0x18006a4ba  test    rsi, rsi
0x18006a4bd  jz      short loc_18006A4C1
0x18006a4bf  mov     [rsi], eax
0x18006a4c1  mov     [r14], eax
0x18006a4c4  mov     r14d, 1
0x18006a4ca  mov     eax, [rbp+460h+arg_28]
0x18006a4d0  sub     eax, r14d
0x18006a4d3  jz      short loc_18006A542
0x18006a4d5  sub     eax, r14d
0x18006a4d8  jz      short loc_18006A542
0x18006a4da  sub     eax, 2
0x18006a4dd  jz      loc_18006A6F2
0x18006a4e3  cmp     eax, 4
0x18006a4e6  jz      short loc_18006A4F7
0x18006a4e8  lea     ecx, [r14+56h]; dwErrCode
0x18006a4ec  call    cs:__imp_SetLastError
0x18006a4f2  jmp     loc_18006A9B2
0x18006a4f7  lea     rcx, aCheckfilecopyo_1; "CheckFileCopyOptions"
0x18006a4fe  test    rbx, rbx
0x18006a501  jz      loc_18006A6DE
0x18006a507  lea     rdx, aOnlyCopyingNew; "Only copying newer driver files"
0x18006a50e  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18006a513  mov     rcx, [r15]; Str
0x18006a516  mov     edx, 5Ch ; '\'; Ch
0x18006a51b  call    cs:__imp_wcsrchr
0x18006a521  test    rax, rax
0x18006a524  jz      short loc_18006A542
0x18006a526  mov     rdx, [rbx+20h]
0x18006a52a  test    rdx, rdx
0x18006a52d  jz      short loc_18006A542
0x18006a52f  lea     rcx, [rax+2]
0x18006a533  call    cs:__imp__o__wcsicmp
0x18006a539  test    eax, eax
0x18006a53b  jnz     short loc_18006A542
0x18006a53d  mov     [rsp+560h+var_52C], r14d
0x18006a542  mov     r14d, 40Ah
0x18006a548  mov     ecx, r14d
0x18006a54b  call    cs:__imp_DllAllocSplMem
0x18006a551  mov     r15, rax
0x18006a554  test    rax, rax
0x18006a557  jz      loc_18006A9B2
0x18006a55d  mov     ecx, r14d
0x18006a560  call    cs:__imp_DllAllocSplMem
0x18006a566  mov     r13, rax
0x18006a569  test    rax, rax
0x18006a56c  jz      loc_18006A99B
0x18006a572  mov     r8, rdi; struct _INIENVIRONMENT *
0x18006a575  mov     edx, 104h; unsigned int
0x18006a57a  mov     rcx, r15; unsigned __int16 *
0x18006a57d  call    ?GetEnvironmentScratchDirectory@@YAKPEAGKPEAU_INIENVIRONMENT@@H@Z; GetEnvironmentScratchDirectory(ushort *,ulong,_INIENVIRONMENT *,int)
0x18006a582  test    eax, eax
0x18006a584  jz      loc_18006A99B
0x18006a58a  mov     r14d, 205h
0x18006a590  lea     r8, SubBlock; "\\"
0x18006a597  mov     edx, r14d; unsigned __int64
0x18006a59a  mov     rcx, r15; unsigned __int16 *
0x18006a59d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006a5a2  mov     ecx, eax
0x18006a5a4  call    BoolFromHResult
0x18006a5a9  test    eax, eax
0x18006a5ab  jz      loc_18006A99B
0x18006a5b1  mov     r8, [rsp+560h+var_508]
0x18006a5b6  mov     edx, r14d; unsigned __int64
0x18006a5b9  mov     rcx, r15; unsigned __int16 *
0x18006a5bc  mov     r8, [r8+18h]; unsigned __int16 *
0x18006a5c0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006a5c5  mov     ecx, eax
0x18006a5c7  call    BoolFromHResult
0x18006a5cc  test    eax, eax
0x18006a5ce  jz      loc_18006A99B
0x18006a5d4  xor     r9d, r9d
0x18006a5d7  lea     r8, aNew; "\\New"
0x18006a5de  mov     rdx, r15
0x18006a5e1  lea     rcx, [rsp+560h+var_510]
0x18006a5e6  call    StrCatAlloc
0x18006a5eb  mov     ecx, eax
0x18006a5ed  call    BoolFromStatus
0x18006a5f2  test    eax, eax
0x18006a5f4  jz      loc_18006A99B
0x18006a5fa  mov     rax, [rdi+18h]
0x18006a5fe  lea     r8, szWin95Environment; "Windows 4.0"
0x18006a605  sub     r8, rax
0x18006a608  movzx   edx, word ptr [rax]
0x18006a60b  movzx   ecx, word ptr [rax+r8]
0x18006a610  sub     edx, ecx
0x18006a612  jnz     short loc_18006A61C
0x18006a614  add     rax, 2
0x18006a618  test    ecx, ecx
0x18006a61a  jnz     short loc_18006A608
0x18006a61c  test    edx, edx
0x18006a61e  jnz     short loc_18006A646
0x18006a620  xor     r9d, r9d
0x18006a623  lea     r8, aColor; "\\Color"
0x18006a62a  mov     rdx, r15
0x18006a62d  lea     rcx, [rsp+560h+var_520]
0x18006a632  call    StrCatAlloc
0x18006a637  mov     ecx, eax
0x18006a639  call    BoolFromStatus
0x18006a63e  test    eax, eax
0x18006a640  jz      loc_18006A99B
0x18006a646  xor     edi, edi
0x18006a648  mov     [rsp+560h+var_530], edi
0x18006a64c  mov     [rsp+560h+var_524], edi
0x18006a650  test    rbx, rbx
0x18006a653  jz      short loc_18006A65E
0x18006a655  lea     rcx, [rbx+10h]; unsigned int *
0x18006a659  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x18006a65e  call    LeaveSplSem
0x18006a663  xor     r14d, r14d
0x18006a666  cmp     [rbp+460h+arg_20], edi
0x18006a66c  jbe     loc_18006A8EC
0x18006a672  mov     rdi, [rsp+560h+var_518]
0x18006a677  lea     rdx, [rbp+460h+FindFileData]; lpFindFileData
0x18006a67e  mov     esi, r14d
0x18006a681  shl     rsi, 5
0x18006a685  mov     rcx, [rsi+rdi]; lpFileName
0x18006a689  call    cs:__imp_FindFirstFileW
0x18006a68f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006a693  jz      loc_18006A981
0x18006a699  mov     rcx, rax; hFindFile
0x18006a69c  call    cs:__imp_FindClose
0x18006a6a2  mov     rcx, [rsi+rdi]; Str
0x18006a6a6  mov     edx, 5Ch ; '\'; Ch
0x18006a6ab  call    cs:__imp_wcsrchr
0x18006a6b1  test    rax, rax
0x18006a6b4  jz      loc_18006A981
0x18006a6ba  lea     rdi, [rax+2]
0x18006a6be  cmp     [rsp+560h+var_520], r12
0x18006a6c3  jz      short loc_18006A702
0x18006a6c5  mov     rcx, [rsp+560h+var_518]
0x18006a6ca  mov     rcx, [rsi+rcx]; unsigned __int16 *
0x18006a6ce  call    ?IsAColorFile@@YAHPEBG@Z; IsAColorFile(ushort const *)
0x18006a6d3  test    eax, eax
0x18006a6d5  jz      short loc_18006A702
0x18006a6d7  mov     r9, [rsp+560h+var_520]
0x18006a6dc  jmp     short loc_18006A74C
0x18006a6de  lea     rdx, aThisIsNotAnUpg; "This is not an upgrade, not doing versi"...
0x18006a6e5  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18006a6ea  mov     r12d, r14d
0x18006a6ed  jmp     loc_18006A9B2
0x18006a6f2  lea     rdx, aCopyingAllFile; "Copying all files, not doing version ch"...
0x18006a6f9  lea     rcx, aCheckfilecopyo_1; "CheckFileCopyOptions"
0x18006a700  jmp     short loc_18006A6E5
0x18006a702  test    r14d, r14d
0x18006a705  jnz     short loc_18006A717
0x18006a707  cmp     [rsp+560h+var_52C], r12d
0x18006a70c  jnz     short loc_18006A717
0x18006a70e  test    rbx, rbx
0x18006a711  jz      short loc_18006A717
0x18006a713  mov     rdi, [rbx+20h]
0x18006a717  mov     r9, [rsp+560h+var_510]
0x18006a71c  lea     r8, aWsWs_6; "%ws\\%ws"
0x18006a723  mov     edx, 205h; unsigned __int64
0x18006a728  mov     [rsp+560h+var_540], rdi
0x18006a72d  mov     rcx, r13; unsigned __int16 *
0x18006a730  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006a735  lea     rdx, [rsp+560h+var_4F0]; lpFindFileData
0x18006a73a  mov     rcx, r13; lpFileName
0x18006a73d  call    cs:__imp_FindFirstFileW
0x18006a743  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006a747  jnz     short loc_18006A7BF
0x18006a749  mov     r9, r15
0x18006a74c  lea     r8, aWsWs_6; "%ws\\%ws"
0x18006a753  mov     [rsp+560h+var_540], rdi
0x18006a758  mov     edx, 205h; unsigned __int64
0x18006a75d  mov     rcx, r13; unsigned __int16 *
0x18006a760  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006a765  lea     rdx, [rsp+560h+var_4F0]; lpFindFileData
0x18006a76a  mov     rcx, r13; lpFileName
0x18006a76d  call    cs:__imp_FindFirstFileW
0x18006a773  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006a777  jnz     short loc_18006A7BF
0x18006a779  test    r14d, r14d
0x18006a77c  jnz     short loc_18006A7B2
0x18006a77e  cmp     [rsp+560h+var_52C], r12d
0x18006a783  jnz     short loc_18006A7B2
0x18006a785  test    rbx, rbx
0x18006a788  jz      short loc_18006A7B2
0x18006a78a  lea     r8, [rbp+460h+FindFileData.cFileName]
0x18006a791  lea     rdx, aDidnTFindWsOnT; "Didn't find %ws on the target, treating"...
0x18006a798  lea     rcx, aCheckfilecopyo_1; "CheckFileCopyOptions"
0x18006a79f  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18006a7a4  mov     edi, 1
0x18006a7a9  mov     [rsp+560h+var_530], edi
0x18006a7ad  jmp     loc_18006A8D7
0x18006a7b2  mov     [rsp+560h+var_524], 1
0x18006a7ba  jmp     loc_18006A8D3
0x18006a7bf  mov     rcx, rax; hFindFile
0x18006a7c2  call    cs:__imp_FindClose
0x18006a7c8  xor     ecx, ecx
0x18006a7ca  call    EnterSplSem
0x18006a7cf  test    rbx, rbx
0x18006a7d2  jz      short loc_18006A7E2
0x18006a7d4  lea     rcx, [rbx+10h]; unsigned int *
0x18006a7d8  cmp     [rcx], r12d
0x18006a7db  jz      short loc_18006A7E2
0x18006a7dd  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x18006a7e2  mov     rcx, [rsp+560h+var_508]; struct _INIVERSION *
0x18006a7e7  lea     r8, [rsp+560h+var_528]; unsigned int *
0x18006a7ec  mov     rdx, r13; unsigned __int16 *
0x18006a7ef  call    ?GetDriverFileCachedVersion@@YAHPEAU_INIVERSION@@PEBGPEAK@Z; GetDriverFileCachedVersion(_INIVERSION *,ushort const *,ulong *)
0x18006a7f4  test    eax, eax
0x18006a7f6  jz      loc_18006A94E
0x18006a7fc  test    rbx, rbx
0x18006a7ff  jz      short loc_18006A80A
0x18006a801  lea     rcx, [rbx+10h]; unsigned int *
0x18006a805  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x18006a80a  call    LeaveSplSem
0x18006a80f  mov     rcx, [rsp+560h+var_518]
0x18006a814  mov     eax, [rsp+560h+var_528]
0x18006a818  cmp     [rsi+rcx+8], eax
0x18006a81c  jnz     short loc_18006A859
0x18006a81e  lea     rdx, [rbp+460h+var_4F0.ftLastWriteTime]; lpFileTime2
0x18006a822  lea     rcx, [rbp+460h+FindFileData.ftLastWriteTime]; lpFileTime1
0x18006a829  call    cs:__imp_CompareFileTime
0x18006a82f  cmp     eax, 1
0x18006a832  jz      short loc_18006A85B
0x18006a834  cmp     eax, 0FFFFFFFFh
0x18006a837  jz      short loc_18006A892
0x18006a839  lea     r9, [rbp+460h+FindFileData.cFileName]
0x18006a840  lea     r8, [rbp+460h+var_4F0.cFileName]
0x18006a844  lea     rdx, aTargetWsIsTheS; "Target %ws is the same as %ws"
0x18006a84b  lea     rcx, aCheckfilecopyo_1; "CheckFileCopyOptions"
0x18006a852  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18006a857  jmp     short loc_18006A8D3
0x18006a859  jbe     short loc_18006A892
0x18006a85b  lea     r9, [rbp+460h+var_4F0.cFileName]
0x18006a85f  lea     r8, [rbp+460h+FindFileData.cFileName]
0x18006a866  lea     rdx, aSourceWsIsNewe; "Source %ws is newer than %ws"
0x18006a86d  lea     rcx, aCheckfilecopyo_1; "CheckFileCopyOptions"
0x18006a874  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18006a879  cmp     [rbp+460h+arg_28], 2
0x18006a880  jnz     loc_18006A7A4
0x18006a886  lea     rdx, aThereIsANewerS; "There is a newer source file, so the dr"...
0x18006a88d  jmp     loc_18006A935
0x18006a892  lea     r9, [rbp+460h+FindFileData.cFileName]
0x18006a899  lea     r8, [rbp+460h+var_4F0.cFileName]
0x18006a89d  lea     rdx, aTargetWsIsNewe; "Target %ws is newer than %ws"
0x18006a8a4  lea     rcx, aCheckfilecopyo_1; "CheckFileCopyOptions"
0x18006a8ab  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18006a8b0  cmp     [rbp+460h+arg_28], 1
0x18006a8b7  jz      short loc_18006A92E
0x18006a8b9  cmp     [rbp+460h+arg_28], 8
0x18006a8c0  jnz     short loc_18006A8D3
0x18006a8c2  test    r14d, r14d
0x18006a8c5  jnz     short loc_18006A8D3
0x18006a8c7  cmp     [rsp+560h+var_52C], r12d
0x18006a8cc  jnz     short loc_18006A8D3
0x18006a8ce  test    rbx, rbx
0x18006a8d1  jnz     short loc_18006A90E
0x18006a8d3  mov     edi, [rsp+560h+var_530]
0x18006a8d7  inc     r14d
0x18006a8da  cmp     r14d, [rbp+460h+arg_20]
0x18006a8e1  jb      loc_18006A672
0x18006a8e7  mov     rsi, [rsp+560h+var_4F8]
0x18006a8ec  cmp     [rbp+460h+arg_28], 8
0x18006a8f3  jnz     short loc_18006A968
0x18006a8f5  test    edi, edi
0x18006a8f7  jnz     short loc_18006A968
0x18006a8f9  test    rbx, rbx
0x18006a8fc  jz      short loc_18006A968
  ... truncated ...
```
