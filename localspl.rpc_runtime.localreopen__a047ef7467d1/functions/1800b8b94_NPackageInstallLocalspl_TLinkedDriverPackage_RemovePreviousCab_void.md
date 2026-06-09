# NPackageInstallLocalspl::TLinkedDriverPackage::RemovePreviousCab(void)

- ea: `0x1800b8b94`
- end: `0x1800b8fd2`
- name: `?RemovePreviousCab@TLinkedDriverPackage@NPackageInstallLocalspl@@QEAAJXZ`
- size: `1086`
- prototype: `__int64 __fastcall(NPackageInstallLocalspl::TLinkedDriverPackage *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x18000f270`
- `0x1800aca48`

## callees

- `0x180011f00`
- `0x18001fb10`
- `0x18001feb4`
- `0x18003e984`
- `0x18003ea2c`
- `0x180046650`
- `0x180047330`
- `0x1800b8b94`
- `0x1800ccbd8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800b8d92`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800b8d92`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800b8c21`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800b8c8e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800b8c21`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800b8c8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8e11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8e11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8eaa`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800b8dcb`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800b8dcb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b8df2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b8df2`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800b8f68`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800b8f68`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800b8d21`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800b8d21`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800b8f79`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800b8f79`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800b8e9c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800b8e9c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800b8dab`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800b8dab`

## string_xrefs

- `0x1800b8eba`: `MoveFileEx %ws failed with error code %d`
- `0x1800b8c5f`: `NPackageInstallLocalspl::TLinkedDriverPackage::RemovePreviousCab`
- `0x1800b8ccc`: `NPackageInstallLocalspl::TLinkedDriverPackage::RemovePreviousCab`
- `0x1800b8ddf`: `NPackageInstallLocalspl::TLinkedDriverPackage::RemovePreviousCab`
- `0x1800b8ec3`: `NPackageInstallLocalspl::TLinkedDriverPackage::RemovePreviousCab`
- `0x1800b8f9f`: `NPackageInstallLocalspl::TLinkedDriverPackage::RemovePreviousCab`
- `0x1800b8cc3`: `Cab directory is '%ws', hr : 0x%x`
- `0x1800b8f85`: `m_strCabPath '%ws' is in invalid format, hr : 0x%x`
- `0x1800b8dd8`: `Attempt to delete cab file %ws `

## pseudocode

```c
__int64 __fastcall NPackageInstallLocalspl::TLinkedDriverPackage::RemovePreviousCab(
        NPackageInstallLocalspl::TLinkedDriverPackage *this)
{
  const unsigned __int16 *v2; // rdi
  wchar_t *v3; // rax
  wchar_t *v4; // r14
  __int64 v5; // rdi
  const unsigned __int16 *v6; // r14
  wchar_t *v7; // rax
  wchar_t *v8; // r15
  HANDLE FirstFileW; // r15
  DWORD LastError; // eax
  struct SplLogType *v11; // rax
  DWORD v12; // ebx
  struct SplLogType *v13; // rax
  const wchar_t *v15; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h]
  int v17; // [rsp+50h] [rbp-B0h]
  int v18; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v19; // [rsp+60h] [rbp-A0h]
  int v20; // [rsp+68h] [rbp-98h]
  DWORD v21; // [rsp+70h] [rbp-90h] BYREF
  __int64 v22; // [rsp+78h] [rbp-88h]
  int v23; // [rsp+80h] [rbp-80h]
  const wchar_t *v24; // [rsp+88h] [rbp-78h] BYREF
  __int64 v25; // [rsp+90h] [rbp-70h]
  int v26; // [rsp+98h] [rbp-68h]
  _BYTE v27[32]; // [rsp+A0h] [rbp-60h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR FileName[264]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v30[264]; // [rsp+520h] [rbp+420h] BYREF
  wchar_t SubStr[264]; // [rsp+730h] [rbp+630h] BYREF

  memset_0(SubStr, 0, 0x208u);
  memset_0(v30, 0, 0x208u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(FileName, 0, 0x208u);
  v2 = (const unsigned __int16 *)*((_QWORD *)this + 5);
  if ( !v2 || (v3 = wcsrchr(*((const wchar_t **)this + 5), 0x5Fu), (v4 = v3) == 0) )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "NPackageInstallLocalspl::TLinkedDriverPackage::RemovePreviousCab",
      L"m_strPackageID '%ws' is in invalid format, hr : 0x%x",
      *((_QWORD *)this + 5),
      0);
    goto LABEL_22;
  }
  *v3 = 0;
  v5 = (unsigned int)StringCchCopyW(SubStr, 0x104u, v2);
  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "NPackageInstallLocalspl::TLinkedDriverPackage::RemovePreviousCab",
    L"Cab prefix is '%ws', hr: 0x%x",
    SubStr,
    v5);
  *v4 = 95;
  if ( (int)v5 < 0 )
    return (unsigned int)v5;
  v6 = (const unsigned __int16 *)*((_QWORD *)this + 7);
  if ( !v6 || (v7 = wcsrchr(*((const wchar_t **)this + 7), 0x5Cu), (v8 = v7) == 0) )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "NPackageInstallLocalspl::TLinkedDriverPackage::RemovePreviousCab",
      L"m_strCabPath '%ws' is in invalid format, hr : 0x%x",
      *((_QWORD *)this + 7),
      (unsigned int)v5);
LABEL_22:
    LODWORD(v5) = -2147024809;
    return (unsigned int)v5;
  }
  *v7 = 0;
  v5 = (unsigned int)StringCchCopyW(v30, 0x104u, v6);
  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "NPackageInstallLocalspl::TLinkedDriverPackage::RemovePreviousCab",
    L"Cab directory is '%ws', hr : 0x%x",
    v30,
    v5);
  *v8 = 92;
  if ( (int)v5 >= 0 )
  {
    LODWORD(v5) = NCoreLibrary::StrNCatBuff(
                    (NCoreLibrary *)FileName,
                    (unsigned __int16 *)0x104,
                    (unsigned int)v30,
                    L"\\*",
                    0);
    if ( (int)v5 >= 0 )
    {
      FirstFileW = FindFirstFileW(FileName, &FindFileData);
      if ( FirstFileW != (HANDLE)-1LL )
      {
        do
        {
          if ( (FindFileData.dwFileAttributes & 0x10) == 0
            && !(unsigned int)NCoreLibrary::StrNCatBuff(
                                (NCoreLibrary *)FileName,
                                (unsigned __int16 *)0x104,
                                (unsigned int)v30,
                                L"\\",
                                FindFileData.cFileName,
                                0)
            && wcsstr(FileName, SubStr)
            && lstrcmpiW(FileName, v6) )
          {
            if ( (FindFileData.dwFileAttributes & 1) != 0 )
              SetFileAttributesW(FileName, FindFileData.dwFileAttributes & 0xFFFFFFFE);
            LocalSpoolerTelemetry::WriteDbgTraceInfo(
              "NPackageInstallLocalspl::TLinkedDriverPackage::RemovePreviousCab",
              L"Attempt to delete cab file %ws ",
              FileName);
            if ( !DeleteFileW(FileName) )
            {
              LODWORD(v15) = 104;
              v16 = 4;
              v17 = 0;
              LastError = GetLastError();
              v19 = 4;
              v18 = LastError;
              v20 = 0;
              v21 = 0;
              v22 = 4;
              v23 = 0;
              v24 = L"-";
              v25 = 4;
              v26 = 1;
              v11 = SplLogType::SplLogType((SplLogType *)v27, FileName);
              SplLogEvent2(&SPOOLER_DELETE_FILE_FAILED, v11, &v24, &v21, &v18, &v15, 0);
              if ( !MoveFileExW(FileName, 0, 4u) )
              {
                v12 = GetLastError();
                LocalSpoolerTelemetry::WriteDbgTraceError(
                  "NPackageInstallLocalspl::TLinkedDriverPackage::RemovePreviousCab",
                  L"MoveFileEx %ws failed with error code %d",
                  FileName,
                  v12);
                v21 = v12;
                LODWORD(v24) = 103;
                v15 = L"-";
                v25 = 4;
                v26 = 0;
                v22 = 4;
                v23 = 0;
                v18 = 4;
                v19 = 4;
                v20 = 0;
                v16 = 4;
                v17 = 1;
                v13 = SplLogType::SplLogType((SplLogType *)v27, FileName);
                SplLogEvent2(&SPOOLER_MOVE_FILE_FAILED, v13, &v15, &v18, &v21, &v24, 0);
              }
            }
          }
        }
        while ( FindNextFileW(FirstFileW, &FindFileData) );
        FindClose(FirstFileW);
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800b8b94  push    rbp
0x1800b8b96  push    rbx
0x1800b8b97  push    rdi
0x1800b8b98  push    r13
0x1800b8b9a  push    r14
0x1800b8b9c  push    r15
0x1800b8b9e  lea     rbp, [rsp-858h]
0x1800b8ba6  sub     rsp, 958h
0x1800b8bad  mov     rax, cs:__security_cookie
0x1800b8bb4  xor     rax, rsp
0x1800b8bb7  mov     [rbp+880h+var_40], rax
0x1800b8bbe  mov     rbx, rcx
0x1800b8bc1  mov     edi, 208h
0x1800b8bc6  mov     r8d, edi; Size
0x1800b8bc9  lea     rcx, [rbp+880h+SubStr]; void *
0x1800b8bd0  xor     edx, edx; Val
0x1800b8bd2  call    memset_0
0x1800b8bd7  mov     r8d, edi; Size
0x1800b8bda  lea     rcx, [rbp+880h+var_460]; void *
0x1800b8be1  xor     edx, edx; Val
0x1800b8be3  call    memset_0
0x1800b8be8  xor     edx, edx; Val
0x1800b8bea  lea     r8d, [rdi+48h]; Size
0x1800b8bee  lea     rcx, [rbp+880h+FindFileData]; void *
0x1800b8bf2  call    memset_0
0x1800b8bf7  mov     r8d, edi; Size
0x1800b8bfa  lea     rcx, [rbp+880h+FileName]; void *
0x1800b8c01  xor     edx, edx; Val
0x1800b8c03  call    memset_0
0x1800b8c08  mov     rdi, [rbx+28h]
0x1800b8c0c  test    rdi, rdi
0x1800b8c0f  jz      loc_1800B8F91
0x1800b8c15  mov     r15d, 5Fh ; '_'
0x1800b8c1b  mov     rcx, rdi; Str
0x1800b8c1e  mov     edx, r15d; Ch
0x1800b8c21  call    cs:__imp_wcsrchr
0x1800b8c27  mov     r14, rax
0x1800b8c2a  test    rax, rax
0x1800b8c2d  jz      loc_1800B8F91
0x1800b8c33  xor     ecx, ecx
0x1800b8c35  mov     r8, rdi; unsigned __int16 *
0x1800b8c38  mov     [rax], cx
0x1800b8c3b  mov     edx, 104h; unsigned __int64
0x1800b8c40  lea     rcx, [rbp+880h+SubStr]; unsigned __int16 *
0x1800b8c47  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b8c4c  mov     r9d, eax
0x1800b8c4f  lea     r8, [rbp+880h+SubStr]
0x1800b8c56  lea     rdx, aCabPrefixIsWsH; "Cab prefix is '%ws', hr: 0x%x"
0x1800b8c5d  mov     edi, eax
0x1800b8c5f  lea     rcx, aNpackageinstal_3; "NPackageInstallLocalspl::TLinkedDriverP"...
0x1800b8c66  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800b8c6b  mov     [r14], r15w
0x1800b8c6f  test    edi, edi
0x1800b8c71  js      loc_1800B8FB0
0x1800b8c77  mov     r14, [rbx+38h]
0x1800b8c7b  test    r14, r14
0x1800b8c7e  jz      loc_1800B8F81
0x1800b8c84  lea     r13d, [r15-3]
0x1800b8c88  mov     rcx, r14; Str
0x1800b8c8b  mov     edx, r13d; Ch
0x1800b8c8e  call    cs:__imp_wcsrchr
0x1800b8c94  mov     r15, rax
0x1800b8c97  test    rax, rax
0x1800b8c9a  jz      loc_1800B8F81
0x1800b8ca0  xor     ecx, ecx
0x1800b8ca2  mov     r8, r14; unsigned __int16 *
0x1800b8ca5  mov     [rax], cx
0x1800b8ca8  mov     edx, 104h; unsigned __int64
0x1800b8cad  lea     rcx, [rbp+880h+var_460]; unsigned __int16 *
0x1800b8cb4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b8cb9  mov     r9d, eax
0x1800b8cbc  lea     r8, [rbp+880h+var_460]
0x1800b8cc3  lea     rdx, aCabDirectoryIs; "Cab directory is '%ws', hr : 0x%x"
0x1800b8cca  mov     edi, eax
0x1800b8ccc  lea     rcx, aNpackageinstal_3; "NPackageInstallLocalspl::TLinkedDriverP"...
0x1800b8cd3  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800b8cd8  mov     [r15], r13w
0x1800b8cdc  test    edi, edi
0x1800b8cde  js      loc_1800B8FB0
0x1800b8ce4  lea     r9, asc_1800FF25C; "\\*"
0x1800b8ceb  mov     [rsp+980h+var_960], 0
0x1800b8cf4  lea     r8, [rbp+880h+var_460]; unsigned int
0x1800b8cfb  mov     edx, 104h; unsigned __int16 *
0x1800b8d00  lea     rcx, [rbp+880h+FileName]; this
0x1800b8d07  call    ?StrNCatBuff@NCoreLibrary@@YAJPEAGIZZ; NCoreLibrary::StrNCatBuff(ushort *,uint,...)
0x1800b8d0c  mov     edi, eax
0x1800b8d0e  test    eax, eax
0x1800b8d10  js      loc_1800B8FB0
0x1800b8d16  lea     rdx, [rbp+880h+FindFileData]; lpFindFileData
0x1800b8d1a  lea     rcx, [rbp+880h+FileName]; lpFileName
0x1800b8d21  call    cs:__imp_FindFirstFileW
0x1800b8d27  mov     r15, rax
0x1800b8d2a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b8d2e  jz      loc_1800B8FB0
0x1800b8d34  mov     r13d, 4
0x1800b8d3a  lea     rbx, asc_1800ECF90; "-"
0x1800b8d41  test    byte ptr [rbp+880h+FindFileData.dwFileAttributes], 10h
0x1800b8d45  jnz     loc_1800B8F61
0x1800b8d4b  lea     rax, [rbp+880h+FindFileData.cFileName]
0x1800b8d4f  mov     [rsp+980h+var_958], 0
0x1800b8d58  lea     r9, SubBlock; "\\"
0x1800b8d5f  mov     [rsp+980h+var_960], rax
0x1800b8d64  lea     r8, [rbp+880h+var_460]; unsigned int
0x1800b8d6b  mov     edx, 104h; unsigned __int16 *
0x1800b8d70  lea     rcx, [rbp+880h+FileName]; this
0x1800b8d77  call    ?StrNCatBuff@NCoreLibrary@@YAJPEAGIZZ; NCoreLibrary::StrNCatBuff(ushort *,uint,...)
0x1800b8d7c  test    eax, eax
0x1800b8d7e  jnz     loc_1800B8F61
0x1800b8d84  lea     rdx, [rbp+880h+SubStr]; SubStr
0x1800b8d8b  lea     rcx, [rbp+880h+FileName]; Str
0x1800b8d92  call    cs:__imp_wcsstr
0x1800b8d98  test    rax, rax
0x1800b8d9b  jz      loc_1800B8F61
0x1800b8da1  mov     rdx, r14; lpString2
0x1800b8da4  lea     rcx, [rbp+880h+FileName]; lpString1
0x1800b8dab  call    cs:__imp_lstrcmpiW
0x1800b8db1  test    eax, eax
0x1800b8db3  jz      loc_1800B8F61
0x1800b8db9  mov     edx, [rbp+880h+FindFileData.dwFileAttributes]
0x1800b8dbc  test    dl, 1
0x1800b8dbf  jz      short loc_1800B8DD1
0x1800b8dc1  and     edx, 0FFFFFFFEh; dwFileAttributes
0x1800b8dc4  lea     rcx, [rbp+880h+FileName]; lpFileName
0x1800b8dcb  call    cs:__imp_SetFileAttributesW
0x1800b8dd1  lea     r8, [rbp+880h+FileName]
0x1800b8dd8  lea     rdx, aAttemptToDelet; "Attempt to delete cab file %ws "
0x1800b8ddf  lea     rcx, aNpackageinstal_3; "NPackageInstallLocalspl::TLinkedDriverP"...
0x1800b8de6  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800b8deb  lea     rcx, [rbp+880h+FileName]; lpFileName
0x1800b8df2  call    cs:__imp_DeleteFileW
0x1800b8df8  test    eax, eax
0x1800b8dfa  jnz     loc_1800B8F61
0x1800b8e00  mov     dword ptr [rsp+980h+var_940], 68h ; 'h'
0x1800b8e08  mov     [rsp+980h+var_938], r13
0x1800b8e0d  mov     [rsp+980h+var_930], eax
0x1800b8e11  call    cs:__imp_GetLastError
0x1800b8e17  lea     rdx, [rbp+880h+FileName]; unsigned __int16 *
0x1800b8e1e  mov     [rsp+980h+var_920], r13
0x1800b8e23  lea     rcx, [rbp+880h+var_8E0]; this
0x1800b8e27  mov     [rsp+980h+var_928], eax
0x1800b8e2b  mov     [rsp+980h+var_918], 0
0x1800b8e33  mov     [rsp+980h+var_910], 0
0x1800b8e3b  mov     [rsp+980h+var_908], r13
0x1800b8e40  mov     [rbp+880h+var_900], 0
0x1800b8e47  mov     [rbp+880h+var_8F8], rbx
0x1800b8e4b  mov     [rbp+880h+var_8F0], r13
0x1800b8e4f  mov     [rbp+880h+var_8E8], 1
0x1800b8e56  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x1800b8e5b  lea     rcx, [rsp+980h+var_940]
0x1800b8e60  mov     [rsp+980h+var_950], 0
0x1800b8e69  mov     [rsp+980h+var_958], rcx
0x1800b8e6e  lea     r9, [rsp+980h+var_910]
0x1800b8e73  lea     rcx, [rsp+980h+var_928]
0x1800b8e78  mov     rdx, rax; struct SplLogType *
0x1800b8e7b  mov     [rsp+980h+var_960], rcx
0x1800b8e80  lea     r8, [rbp+880h+var_8F8]
0x1800b8e84  lea     rcx, SPOOLER_DELETE_FILE_FAILED; struct _EVENT_DESCRIPTOR *
0x1800b8e8b  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x1800b8e90  mov     r8d, r13d; dwFlags
0x1800b8e93  lea     rcx, [rbp+880h+FileName]; lpExistingFileName
0x1800b8e9a  xor     edx, edx; lpNewFileName
0x1800b8e9c  call    cs:__imp_MoveFileExW
0x1800b8ea2  test    eax, eax
0x1800b8ea4  jnz     loc_1800B8F61
0x1800b8eaa  call    cs:__imp_GetLastError
0x1800b8eb0  mov     r9d, eax
0x1800b8eb3  lea     r8, [rbp+880h+FileName]
0x1800b8eba  lea     rdx, aMovefileexWsFa; "MoveFileEx %ws failed with error code %"...
0x1800b8ec1  mov     ebx, eax
0x1800b8ec3  lea     rcx, aNpackageinstal_3; "NPackageInstallLocalspl::TLinkedDriverP"...
0x1800b8eca  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800b8ecf  mov     [rsp+980h+var_910], ebx
0x1800b8ed3  lea     rdx, [rbp+880h+FileName]; unsigned __int16 *
0x1800b8eda  lea     rbx, asc_1800ECF90; "-"
0x1800b8ee1  mov     dword ptr [rbp+880h+var_8F8], 67h ; 'g'
0x1800b8ee8  lea     rcx, [rbp+880h+var_8E0]; this
0x1800b8eec  mov     [rsp+980h+var_940], rbx
0x1800b8ef1  mov     [rbp+880h+var_8F0], r13
0x1800b8ef5  mov     [rbp+880h+var_8E8], 0
0x1800b8efc  mov     [rsp+980h+var_908], r13
0x1800b8f01  mov     [rbp+880h+var_900], 0
0x1800b8f08  mov     [rsp+980h+var_928], r13d
0x1800b8f0d  mov     [rsp+980h+var_920], r13
0x1800b8f12  mov     [rsp+980h+var_918], 0
0x1800b8f1a  mov     [rsp+980h+var_938], r13
0x1800b8f1f  mov     [rsp+980h+var_930], 1
0x1800b8f27  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x1800b8f2c  lea     rcx, [rbp+880h+var_8F8]
0x1800b8f30  mov     [rsp+980h+var_950], 0
0x1800b8f39  mov     [rsp+980h+var_958], rcx
0x1800b8f3e  lea     r9, [rsp+980h+var_928]
0x1800b8f43  lea     rcx, [rsp+980h+var_910]
0x1800b8f48  mov     rdx, rax; struct SplLogType *
0x1800b8f4b  mov     [rsp+980h+var_960], rcx
0x1800b8f50  lea     r8, [rsp+980h+var_940]
0x1800b8f55  lea     rcx, SPOOLER_MOVE_FILE_FAILED; struct _EVENT_DESCRIPTOR *
0x1800b8f5c  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x1800b8f61  lea     rdx, [rbp+880h+FindFileData]; lpFindFileData
0x1800b8f65  mov     rcx, r15; hFindFile
0x1800b8f68  call    cs:__imp_FindNextFileW
0x1800b8f6e  test    eax, eax
0x1800b8f70  jnz     loc_1800B8D41
0x1800b8f76  mov     rcx, r15; hFindFile
0x1800b8f79  call    cs:__imp_FindClose
0x1800b8f7f  jmp     short loc_1800B8FB0
0x1800b8f81  mov     r8, [rbx+38h]
0x1800b8f85  lea     rdx, aMStrcabpathWsI; "m_strCabPath '%ws' is in invalid format"...
0x1800b8f8c  mov     r9d, edi
0x1800b8f8f  jmp     short loc_1800B8F9F
0x1800b8f91  mov     r8, [rbx+28h]
0x1800b8f95  lea     rdx, aMStrpackageidW; "m_strPackageID '%ws' is in invalid form"...
0x1800b8f9c  xor     r9d, r9d
0x1800b8f9f  lea     rcx, aNpackageinstal_3; "NPackageInstallLocalspl::TLinkedDriverP"...
0x1800b8fa6  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800b8fab  mov     edi, 80070057h
0x1800b8fb0  mov     eax, edi
0x1800b8fb2  mov     rcx, [rbp+880h+var_40]
0x1800b8fb9  xor     rcx, rsp; StackCookie
0x1800b8fbc  call    __security_check_cookie
0x1800b8fc1  add     rsp, 958h
0x1800b8fc8  pop     r15
0x1800b8fca  pop     r14
0x1800b8fcc  pop     r13
0x1800b8fce  pop     rdi
0x1800b8fcf  pop     rbx
0x1800b8fd0  pop     rbp
0x1800b8fd1  retn
```
