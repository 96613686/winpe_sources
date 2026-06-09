# CDtcInstanceConfig::InitializeLog(ushort *,long,ulong *)

- ea: `0x18001664c`
- end: `0x180016c71`
- name: `?InitializeLog@CDtcInstanceConfig@@AEAAJPEAGJPEAK@Z`
- size: `1573`
- prototype: `int(CDtcInstanceConfig *__hidden this, unsigned __int16 *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004b750`

## callees

- `0x180003cf0`
- `0x18000d5f4`
- `0x180015f84`
- `0x18001664c`
- `0x18004a774`
- `0x18004ac04`
- `0x18004ad38`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800168de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800168de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a3c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180016baf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180016baf`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180016713`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800168d0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180016713`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800168d0`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180016a32`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180016bc2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180016a32`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180016bc2`
- `SHELL32!__imp_SHCreateDirectory` at `0x18001678d`
- `SHELL32!__imp_SHCreateDirectory` at `0x18001678d`

## string_xrefs

- `0x1800166ca`: `CDtcInstanceConfig::InitializeLog`
- `0x18001675e`: `CDtcInstanceConfig::InitializeLog`
- `0x1800167c0`: `CDtcInstanceConfig::InitializeLog`
- `0x180016808`: `CDtcInstanceConfig::InitializeLog`
- `0x180016886`: `CDtcInstanceConfig::InitializeLog`
- `0x180016916`: `CDtcInstanceConfig::InitializeLog`
- `0x180016a88`: `CDtcInstanceConfig::InitializeLog`
- `0x180016ada`: `CDtcInstanceConfig::InitializeLog`
- `0x180016b84`: `CDtcInstanceConfig::InitializeLog`
- `0x180016bf6`: `CDtcInstanceConfig::InitializeLog`
- `0x180016c27`: `CDtcInstanceConfig::InitializeLog`
- `0x1800166c3`: `com\complus\dtc\dtc\msdtcprx\src\dtcinstanceconfig.cpp`
- `0x180016757`: `com\complus\dtc\dtc\msdtcprx\src\dtcinstanceconfig.cpp`
- `0x180016798`: `com\complus\dtc\dtc\msdtcprx\src\dtcinstanceconfig.cpp`
- `0x18001687f`: `com\complus\dtc\dtc\msdtcprx\src\dtcinstanceconfig.cpp`
- `0x18001690f`: `com\complus\dtc\dtc\msdtcprx\src\dtcinstanceconfig.cpp`
- `0x180016a63`: `com\complus\dtc\dtc\msdtcprx\src\dtcinstanceconfig.cpp`
- `0x180016ab3`: `com\complus\dtc\dtc\msdtcprx\src\dtcinstanceconfig.cpp`
- `0x180016b7d`: `com\complus\dtc\dtc\msdtcprx\src\dtcinstanceconfig.cpp`
- `0x180016be6`: `com\complus\dtc\dtc\msdtcprx\src\dtcinstanceconfig.cpp`
- `0x180016c20`: `com\complus\dtc\dtc\msdtcprx\src\dtcinstanceconfig.cpp`
- `0x1800167ab`: `Could not create log file path %s`
- `0x180016871`: `Path does not exist and pdwErrorHandleMask=%d is not set to create it`
- `0x180016a7c`: `Unable to move the old log (%s) to backup (%s)`
- `0x18001668e`: `DisableDTCLogOverwrite`
- `0x1800166f2`: `CDtcInstanceConfig::InitializeLog (com\complus\dtc\dtc\msdtcprx\src\dtcinstanceconfig.cpp@660): pdwErrorHandleMask`
- `0x1800167f1`: `The logfile path created at %s`
- `0x1800168b7`: `Invalid directory %s`
- `0x180016991`: `SetSddlOnLogDirectory failed`
- `0x180016b43`: `SetSddlOnLogDirectory failed`
- `0x1800169ac`: `File already exists, set dwErrorHandleMask|=%d to overwrite it.`
- `0x180016aca`: `File %s already exists and moved to %s`
- `0x180016bda`: `Directory with the same name as the log file name exists (%s)`
- `0x180016b6b`: `CreateLog failed`

## pseudocode

```c
__int64 __fastcall CDtcInstanceConfig::InitializeLog(
        CDtcInstanceConfig *this,
        unsigned __int16 *a2,
        int a3,
        unsigned int *a4)
{
  int v7; // r14d
  unsigned int v8; // r12d
  DWORD FileAttributesW; // eax
  CDtcInstanceConfig *v10; // rcx
  signed int LastError; // ebx
  const wchar_t *v12; // rax
  __int64 v13; // r9
  int v14; // r14d
  unsigned int v15; // eax
  __int64 v16; // r9
  const wchar_t *v17; // rax
  DWORD v18; // eax
  CDtcInstanceConfig *v19; // rcx
  int v20; // r14d
  const wchar_t *v21; // rax
  __int64 v22; // r9
  signed int v23; // eax
  const wchar_t *v24; // rax
  __int64 v25; // r9
  __int64 v27; // [rsp+28h] [rbp-D8h]
  WCHAR *v28; // [rsp+38h] [rbp-C8h]
  int v29; // [rsp+50h] [rbp-B0h]
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR NewFileName[264]; // [rsp+270h] [rbp+170h] BYREF

  v7 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 344LL))(
         *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
         L"DisableDTCLogOverwrite",
         0);
  v29 = v7;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
    658,
    L"CDtcInstanceConfig::InitializeLog",
    0,
    L"In");
  if ( !a4 )
    DtcInternalErrorW(
      L"CDtcInstanceConfig::InitializeLog (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp@660): pdwErrorHandleMask");
  v8 = *a4 & 2;
  FileAttributesW = GetFileAttributesW(a2);
  if ( FileAttributesW != -1 )
  {
    if ( (FileAttributesW & 0x10) != 0 )
      goto LABEL_16;
    LastError = -2147024809;
    v28 = a2;
    v17 = L"Invalid directory %s";
    v16 = 707;
LABEL_21:
    LODWORD(v27) = LastError;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
      v16,
      L"CDtcInstanceConfig::InitializeLog",
      v27,
      v17,
      v28);
    goto LABEL_58;
  }
  LastError = GetLastError();
  if ( (unsigned int)(LastError - 2) > 1 )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"GetFileAttributesW failed.";
    v13 = 697;
    goto LABEL_8;
  }
  if ( (*a4 & 1) == 0 )
  {
    v15 = *a4 | 1;
    *a4 = v15;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    LODWORD(v28) = v15;
    v16 = 690;
    v17 = L"Path does not exist and pdwErrorHandleMask=%d is not set to create it";
    goto LABEL_21;
  }
  v14 = SHCreateDirectory(0, a2);
  if ( v14 )
  {
    LODWORD(v27) = LastError;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
      680,
      L"CDtcInstanceConfig::InitializeLog",
      v27,
      L"Could not create log file path %s",
      a2);
    if ( v14 <= 0 )
    {
      LastError = v14;
      goto LABEL_58;
    }
    LastError = (unsigned __int16)v14;
LABEL_14:
    LastError |= 0x80070000;
    goto LABEL_58;
  }
  TraceStringInline(
    15,
    3,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
    685,
    L"CDtcInstanceConfig::InitializeLog",
    0,
    L"The logfile path created at %s",
    a2);
  v7 = v29;
LABEL_16:
  LastError = CDtcInstanceConfig::GetLogFileName(v10, a2, FileName);
  if ( LastError < 0 )
  {
    v12 = L"GetLogFileName(new) failed";
    v13 = 714;
LABEL_8:
    LODWORD(v27) = LastError;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
      v13,
      L"CDtcInstanceConfig::InitializeLog",
      v27,
      v12);
    goto LABEL_58;
  }
  v18 = GetFileAttributesW(FileName);
  if ( v18 == -1 )
  {
    v20 = 0;
    LastError = GetLastError();
    if ( LastError != 2 )
    {
      LODWORD(v27) = LastError;
      TraceStringInline(
        15,
        1,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
        727,
        L"CDtcInstanceConfig::InitializeLog",
        v27,
        L"GetFileAttributes('%s') failed",
        FileName);
      if ( LastError <= 0 )
        goto LABEL_58;
      LastError = (unsigned __int16)LastError;
      goto LABEL_14;
    }
LABEL_45:
    LastError = (*(__int64 (__fastcall **)(CDtcInstanceConfig *, __int64))(*(_QWORD *)this + 56LL))(this, 1);
    if ( LastError >= 0 )
    {
      LastError = SetSddlOnLogDirectory(*(struct ITmInstance **)(*((_QWORD *)this + 2) + 8LL), a2);
      if ( LastError >= 0 )
      {
        LastError = CDtcInstanceConfig::CreateLog(this, a2, a3, v8 == 0);
        if ( LastError >= 0 )
          goto LABEL_52;
        v24 = L"CreateLog failed";
        v25 = 821;
      }
      else
      {
        v24 = L"SetSddlOnLogDirectory failed";
        v25 = 814;
      }
    }
    else
    {
      v24 = L"StopDtc failed.";
      v25 = 807;
    }
    LODWORD(v27) = LastError;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
      v25,
      L"CDtcInstanceConfig::InitializeLog",
      v27,
      v24);
LABEL_52:
    if ( v20 )
    {
      if ( LastError < 0 )
        MoveFileExW(NewFileName, FileName, 8u);
      else
        DeleteFileW(NewFileName);
    }
    goto LABEL_58;
  }
  if ( (v18 & 0x10) != 0 )
  {
    v22 = 798;
    v28 = FileName;
    v21 = L"Directory with the same name as the log file name exists (%s)";
    goto LABEL_57;
  }
  if ( v7 )
  {
    LastError = (*(__int64 (__fastcall **)(CDtcInstanceConfig *, __int64))(*(_QWORD *)this + 56LL))(this, 1);
    if ( LastError >= 0 )
    {
      LastError = SetSddlOnLogDirectory(*(struct ITmInstance **)(*((_QWORD *)this + 2) + 8LL), a2);
      if ( LastError >= 0 )
        goto LABEL_58;
      v12 = L"SetSddlOnLogDirectory failed";
      v13 = 747;
    }
    else
    {
      v12 = L"StopDtc failed.";
      v13 = 741;
    }
    goto LABEL_8;
  }
  if ( !v8 )
  {
    *a4 |= 2u;
    v21 = L"File already exists, set dwErrorHandleMask|=%d to overwrite it.";
    LODWORD(v28) = 2;
    v22 = 757;
LABEL_57:
    LODWORD(v27) = LastError;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
      v22,
      L"CDtcInstanceConfig::InitializeLog",
      v27,
      v21,
      v28);
    LastError = -2147467259;
    goto LABEL_58;
  }
  LastError = CDtcInstanceConfig::GetLogBackupFileName(v19, a2, NewFileName);
  if ( LastError < 0 )
  {
    v12 = L"GetLogBackupFileName(new) failed";
    v13 = 765;
    goto LABEL_8;
  }
  LastError = (*(__int64 (__fastcall **)(CDtcInstanceConfig *, __int64))(*(_QWORD *)this + 56LL))(this, 1);
  if ( LastError < 0 )
  {
    v12 = L"StopDtc failed.";
    v13 = 773;
    goto LABEL_8;
  }
  if ( MoveFileExW(FileName, NewFileName, 8u) )
  {
    TraceStringInline(
      15,
      6,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
      789,
      L"CDtcInstanceConfig::InitializeLog",
      0,
      L"File %s already exists and moved to %s",
      FileName,
      NewFileName);
    v20 = 1;
    goto LABEL_45;
  }
  v23 = GetLastError();
  LastError = v23;
  if ( v23 > 0 )
    LastError = (unsigned __int16)v23 | 0x80070000;
  LODWORD(v27) = LastError;
  TraceStringInline(
    15,
    1,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
    786,
    L"CDtcInstanceConfig::InitializeLog",
    v27,
    L"Unable to move the old log (%s) to backup (%s)",
    FileName,
    NewFileName);
LABEL_58:
  LODWORD(v27) = LastError;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
    839,
    L"CDtcInstanceConfig::InitializeLog",
    v27,
    L"Out");
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001664c  mov     [rsp-8+arg_10], rbx
0x180016651  push    rbp
0x180016652  push    rsi
0x180016653  push    rdi
0x180016654  push    r12
0x180016656  push    r13
0x180016658  push    r14
0x18001665a  push    r15
0x18001665c  lea     rbp, [rsp-390h]
0x180016664  sub     rsp, 490h
0x18001666b  mov     rax, cs:__security_cookie
0x180016672  xor     rax, rsp
0x180016675  mov     [rbp+3C0h+var_40], rax
0x18001667c  mov     rax, [rcx+10h]
0x180016680  mov     rsi, rcx
0x180016683  mov     [rsp+4C0h+var_46C], r8d
0x180016688  mov     rdi, rdx
0x18001668b  xor     r8d, r8d
0x18001668e  lea     rdx, aDisabledtclogo; "DisableDTCLogOverwrite"
0x180016695  mov     r15, r9
0x180016698  mov     rcx, [rax+8]
0x18001669c  mov     rax, [rcx]
0x18001669f  mov     rax, [rax+158h]
0x1800166a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166ab  mov     r14d, eax
0x1800166ae  mov     [rsp+4C0h+var_470], eax
0x1800166b2  mov     edx, 6
0x1800166b7  lea     rax, aIn_0; "In"
0x1800166be  mov     [rsp+4C0h+var_490], rax
0x1800166c3  lea     r8, aComComplusDtcD_12; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x1800166ca  lea     rax, aCdtcinstanceco_3; "CDtcInstanceConfig::InitializeLog"
0x1800166d1  mov     [rsp+4C0h+var_498], 0
0x1800166da  mov     r9d, 292h
0x1800166e0  mov     [rsp+4C0h+var_4A0], rax
0x1800166e5  lea     ecx, [rdx+9]
0x1800166e8  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800166ed  test    r15, r15
0x1800166f0  jnz     short loc_1800166FF
0x1800166f2  lea     rcx, aCdtcinstanceco_1; "CDtcInstanceConfig::InitializeLog (com"...
0x1800166f9  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800166ff  mov     r12d, [r15]
0x180016702  mov     r13d, 0
0x180016708  and     r12d, 2
0x18001670c  mov     rcx, rdi; lpFileName
0x18001670f  setz    r13b
0x180016713  call    cs:__imp_GetFileAttributesW
0x180016719  cmp     eax, 0FFFFFFFFh
0x18001671c  jnz     loc_1800168A5
0x180016722  call    cs:__imp_GetLastError
0x180016728  mov     ebx, eax
0x18001672a  mov     ecx, 1
0x18001672f  add     eax, 0FFFFFFFEh
0x180016732  cmp     eax, ecx
0x180016734  jbe     short loc_18001677D
0x180016736  test    ebx, ebx
0x180016738  jle     short loc_180016743
0x18001673a  movzx   ebx, bx
0x18001673d  or      ebx, 80070000h
0x180016743  lea     rax, aGetfileattribu_0; "GetFileAttributesW failed."
0x18001674a  mov     r9d, 2B9h
0x180016750  mov     edx, ecx
0x180016752  mov     [rsp+4C0h+var_490], rax
0x180016757  lea     r8, aComComplusDtcD_12; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18001675e  lea     rax, aCdtcinstanceco_3; "CDtcInstanceConfig::InitializeLog"
0x180016765  mov     dword ptr [rsp+4C0h+var_498], ebx
0x180016769  mov     ecx, 0Fh
0x18001676e  mov     [rsp+4C0h+var_4A0], rax
0x180016773  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180016778  jmp     loc_180016C0F
0x18001677d  mov     eax, [r15]
0x180016780  test    cl, al
0x180016782  jz      loc_180016855
0x180016788  mov     rdx, rdi; pszPath
0x18001678b  xor     ecx, ecx; hwnd
0x18001678d  call    cs:__imp_SHCreateDirectory
0x180016793  mov     [rsp+4C0h+var_488], rdi
0x180016798  lea     r8, aComComplusDtcD_12; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18001679f  mov     r14d, eax
0x1800167a2  mov     ecx, 0Fh
0x1800167a7  test    eax, eax
0x1800167a9  jz      short loc_1800167F1
0x1800167ab  lea     rax, aCouldNotCreate; "Could not create log file path %s"
0x1800167b2  mov     r9d, 2A8h
0x1800167b8  mov     [rsp+4C0h+var_490], rax
0x1800167bd  lea     edx, [rcx-0Eh]
0x1800167c0  lea     rax, aCdtcinstanceco_3; "CDtcInstanceConfig::InitializeLog"
0x1800167c7  mov     dword ptr [rsp+4C0h+var_498], ebx
0x1800167cb  mov     [rsp+4C0h+var_4A0], rax
0x1800167d0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800167d5  test    r14d, r14d
0x1800167d8  jg      short loc_1800167E2
0x1800167da  mov     ebx, r14d
0x1800167dd  jmp     loc_180016C0F
0x1800167e2  movzx   ebx, r14w
0x1800167e6  or      ebx, 80070000h
0x1800167ec  jmp     loc_180016C0F
0x1800167f1  lea     rax, aTheLogfilePath; "The logfile path created at %s"
0x1800167f8  mov     r9d, 2ADh
0x1800167fe  mov     [rsp+4C0h+var_490], rax
0x180016803  mov     edx, 3
0x180016808  lea     rax, aCdtcinstanceco_3; "CDtcInstanceConfig::InitializeLog"
0x18001680f  mov     [rsp+4C0h+var_498], 0
0x180016818  mov     [rsp+4C0h+var_4A0], rax
0x18001681d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180016822  mov     r14d, [rsp+4C0h+var_470]
0x180016827  lea     r8, [rsp+4C0h+FileName]; unsigned __int16 *
0x18001682c  mov     rdx, rdi; unsigned __int16 *
0x18001682f  call    ?GetLogFileName@CDtcInstanceConfig@@AEAAJPEAG0@Z; CDtcInstanceConfig::GetLogFileName(ushort *,ushort *)
0x180016834  mov     ebx, eax
0x180016836  test    eax, eax
0x180016838  jns     loc_1800168CB
0x18001683e  lea     rax, aGetlogfilename_0; "GetLogFileName(new) failed"
0x180016845  mov     r9d, 2CAh
0x18001684b  mov     edx, 1
0x180016850  jmp     loc_180016752
0x180016855  or      eax, ecx
0x180016857  mov     [r15], eax
0x18001685a  test    ebx, ebx
0x18001685c  jle     short loc_180016867
0x18001685e  movzx   ebx, bx
0x180016861  or      ebx, 80070000h
0x180016867  mov     dword ptr [rsp+4C0h+var_488], eax
0x18001686b  mov     r9d, 2B2h
0x180016871  lea     rax, aPathDoesNotExi; "Path does not exist and pdwErrorHandleM"...
0x180016878  mov     edx, ecx
0x18001687a  mov     [rsp+4C0h+var_490], rax
0x18001687f  lea     r8, aComComplusDtcD_12; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180016886  lea     rax, aCdtcinstanceco_3; "CDtcInstanceConfig::InitializeLog"
0x18001688d  mov     dword ptr [rsp+4C0h+var_498], ebx
0x180016891  mov     ecx, 0Fh
0x180016896  mov     [rsp+4C0h+var_4A0], rax
0x18001689b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800168a0  jmp     loc_180016C0F
0x1800168a5  test    al, 10h
0x1800168a7  jnz     loc_180016827
0x1800168ad  mov     ebx, 80070057h
0x1800168b2  mov     [rsp+4C0h+var_488], rdi
0x1800168b7  lea     rax, aInvalidDirecto; "Invalid directory %s"
0x1800168be  mov     r9d, 2C3h
0x1800168c4  mov     edx, 1
0x1800168c9  jmp     short loc_18001687A
0x1800168cb  lea     rcx, [rsp+4C0h+FileName]; lpFileName
0x1800168d0  call    cs:__imp_GetFileAttributesW
0x1800168d6  cmp     eax, 0FFFFFFFFh
0x1800168d9  jnz     short loc_18001693E
0x1800168db  xor     r14d, r14d
0x1800168de  call    cs:__imp_GetLastError
0x1800168e4  mov     ebx, eax
0x1800168e6  cmp     eax, 2
0x1800168e9  jz      loc_180016AFC
0x1800168ef  lea     rax, [rsp+4C0h+FileName]
0x1800168f4  mov     r9d, 2D7h
0x1800168fa  mov     [rsp+4C0h+var_488], rax
0x1800168ff  lea     edx, [r14+1]
0x180016903  lea     rax, aGetfileattribu; "GetFileAttributes('%s') failed"
0x18001690a  mov     [rsp+4C0h+var_490], rax
0x18001690f  lea     r8, aComComplusDtcD_12; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180016916  lea     rax, aCdtcinstanceco_3; "CDtcInstanceConfig::InitializeLog"
0x18001691d  mov     dword ptr [rsp+4C0h+var_498], ebx
0x180016921  lea     ecx, [rdx+0Eh]
0x180016924  mov     [rsp+4C0h+var_4A0], rax
0x180016929  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001692e  test    ebx, ebx
0x180016930  jle     loc_180016C0F
0x180016936  movzx   ebx, bx
0x180016939  jmp     loc_1800167E6
0x18001693e  test    al, 10h
0x180016940  jnz     loc_180016BCA
0x180016946  test    r14d, r14d
0x180016949  jz      short loc_1800169A3
0x18001694b  mov     rax, [rsi]
0x18001694e  mov     edx, 1
0x180016953  mov     rcx, rsi
0x180016956  mov     rax, [rax+38h]
0x18001695a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001695f  mov     ebx, eax
0x180016961  test    eax, eax
0x180016963  jns     short loc_180016977
0x180016965  lea     rax, aStopdtcFailed; "StopDtc failed."
0x18001696c  mov     r9d, 2E5h
0x180016972  jmp     loc_18001684B
0x180016977  mov     rcx, [rsi+10h]
0x18001697b  mov     rdx, rdi; unsigned __int16 *
0x18001697e  mov     rcx, [rcx+8]; struct ITmInstance *
0x180016982  call    ?SetSddlOnLogDirectory@@YAJPEAUITmInstance@@PEAG@Z; SetSddlOnLogDirectory(ITmInstance *,ushort *)
0x180016987  mov     ebx, eax
0x180016989  test    eax, eax
0x18001698b  jns     loc_180016C0F
0x180016991  lea     rax, aSetsddlonlogdi_0; "SetSddlOnLogDirectory failed"
0x180016998  mov     r9d, 2EBh
0x18001699e  jmp     loc_18001684B
0x1800169a3  test    r12d, r12d
0x1800169a6  jnz     short loc_1800169C6
0x1800169a8  or      dword ptr [r15], 2
0x1800169ac  lea     rax, aFileAlreadyExi; "File already exists, set dwErrorHandleM"...
0x1800169b3  mov     dword ptr [rsp+4C0h+var_488], 2
0x1800169bb  mov     r9d, 2F5h
0x1800169c1  jmp     loc_180016BE1
0x1800169c6  lea     r8, [rbp+3C0h+NewFileName]; unsigned __int16 *
0x1800169cd  mov     rdx, rdi; unsigned __int16 *
0x1800169d0  call    ?GetLogBackupFileName@CDtcInstanceConfig@@AEAAJPEAG0@Z; CDtcInstanceConfig::GetLogBackupFileName(ushort *,ushort *)
0x1800169d5  mov     ebx, eax
0x1800169d7  test    eax, eax
0x1800169d9  jns     short loc_1800169ED
0x1800169db  lea     rax, aGetlogbackupfi; "GetLogBackupFileName(new) failed"
0x1800169e2  mov     r9d, 2FDh
0x1800169e8  jmp     loc_18001684B
0x1800169ed  mov     rax, [rsi]
0x1800169f0  mov     r15d, 1
0x1800169f6  mov     edx, r15d
0x1800169f9  mov     rcx, rsi
0x1800169fc  mov     rax, [rax+38h]
0x180016a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a05  mov     ebx, eax
0x180016a07  test    eax, eax
0x180016a09  jns     short loc_180016A20
0x180016a0b  lea     rax, aStopdtcFailed; "StopDtc failed."
0x180016a12  mov     r9d, 305h
0x180016a18  mov     edx, r15d
0x180016a1b  jmp     loc_180016752
0x180016a20  mov     r8d, 8; dwFlags
0x180016a26  lea     rdx, [rbp+3C0h+NewFileName]; lpNewFileName
0x180016a2d  lea     rcx, [rsp+4C0h+FileName]; lpExistingFileName
0x180016a32  call    cs:__imp_MoveFileExW
0x180016a38  test    eax, eax
0x180016a3a  jnz     short loc_180016AA2
0x180016a3c  call    cs:__imp_GetLastError
0x180016a42  mov     ebx, eax
0x180016a44  test    eax, eax
0x180016a46  jle     short loc_180016A51
0x180016a48  movzx   ebx, ax
0x180016a4b  or      ebx, 80070000h
0x180016a51  lea     rax, [rbp+3C0h+NewFileName]
0x180016a58  mov     r9d, 312h
0x180016a5e  mov     [rsp+4C0h+var_480], rax
0x180016a63  lea     r8, aComComplusDtcD_12; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180016a6a  lea     rax, [rsp+4C0h+FileName]
0x180016a6f  mov     edx, r15d
0x180016a72  mov     [rsp+4C0h+var_488], rax
0x180016a77  mov     ecx, 0Fh
0x180016a7c  lea     rax, aUnableToMoveTh; "Unable to move the old log (%s) to back"...
0x180016a83  mov     [rsp+4C0h+var_490], rax
0x180016a88  lea     rax, aCdtcinstanceco_3; "CDtcInstanceConfig::InitializeLog"
0x180016a8f  mov     dword ptr [rsp+4C0h+var_498], ebx
0x180016a93  mov     [rsp+4C0h+var_4A0], rax
0x180016a98  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180016a9d  jmp     loc_180016C0F
0x180016aa2  lea     rax, [rbp+3C0h+NewFileName]
0x180016aa9  mov     edx, 6
0x180016aae  mov     [rsp+4C0h+var_480], rax
0x180016ab3  lea     r8, aComComplusDtcD_12; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180016aba  lea     rax, [rsp+4C0h+FileName]
0x180016abf  mov     r9d, 315h
0x180016ac5  mov     [rsp+4C0h+var_488], rax
0x180016aca  lea     rax, aFileSAlreadyEx; "File %s already exists and moved to %s"
0x180016ad1  mov     [rsp+4C0h+var_490], rax
0x180016ad6  lea     r12d, [rdx+9]
0x180016ada  lea     rax, aCdtcinstanceco_3; "CDtcInstanceConfig::InitializeLog"
0x180016ae1  mov     [rsp+4C0h+var_498], 0
0x180016aea  mov     ecx, r12d
0x180016aed  mov     [rsp+4C0h+var_4A0], rax
0x180016af2  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180016af7  mov     r14d, r15d
0x180016afa  jmp     short loc_180016B06
0x180016afc  mov     r15d, 1
0x180016b02  lea     r12d, [r15+0Eh]
0x180016b06  mov     rax, [rsi]
0x180016b09  mov     edx, r15d
0x180016b0c  mov     rcx, rsi
0x180016b0f  mov     rax, [rax+38h]
0x180016b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b18  mov     ebx, eax
0x180016b1a  test    eax, eax
0x180016b1c  jns     short loc_180016B2D
0x180016b1e  lea     rax, aStopdtcFailed; "StopDtc failed."
0x180016b25  mov     r9d, 327h
0x180016b2b  jmp     short loc_180016B78
0x180016b2d  mov     rcx, [rsi+10h]
0x180016b31  mov     rdx, rdi; unsigned __int16 *
0x180016b34  mov     rcx, [rcx+8]; struct ITmInstance *
0x180016b38  call    ?SetSddlOnLogDirectory@@YAJPEAUITmInstance@@PEAG@Z; SetSddlOnLogDirectory(ITmInstance *,ushort *)
0x180016b3d  mov     ebx, eax
0x180016b3f  test    eax, eax
0x180016b41  jns     short loc_180016B52
0x180016b43  lea     rax, aSetsddlonlogdi_0; "SetSddlOnLogDirectory failed"
0x180016b4a  mov     r9d, 32Eh
0x180016b50  jmp     short loc_180016B78
0x180016b52  mov     r8d, [rsp+4C0h+var_46C]; int
0x180016b57  mov     r9d, r13d; int
0x180016b5a  mov     rdx, rdi; unsigned __int16 *
0x180016b5d  mov     rcx, rsi; this
0x180016b60  call    ?CreateLog@CDtcInstanceConfig@@AEAAJPEAGHH@Z; CDtcInstanceConfig::CreateLog(ushort *,int,int)
0x180016b65  mov     ebx, eax
0x180016b67  test    eax, eax
0x180016b69  jns     short loc_180016B9F
0x180016b6b  lea     rax, aCreatelogFaile; "CreateLog failed"
0x180016b72  mov     r9d, 335h
0x180016b78  mov     [rsp+4C0h+var_490], rax
0x180016b7d  lea     r8, aComComplusDtcD_12; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180016b84  lea     rax, aCdtcinstanceco_3; "CDtcInstanceConfig::InitializeLog"
  ... truncated ...
```
