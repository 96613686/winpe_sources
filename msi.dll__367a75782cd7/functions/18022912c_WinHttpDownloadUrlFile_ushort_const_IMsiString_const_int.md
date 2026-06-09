# WinHttpDownloadUrlFile(ushort const *,IMsiString const * &,int)

- ea: `0x18022912c`
- end: `0x180229b27`
- name: `?WinHttpDownloadUrlFile@@YAKPEBGAEAPEBVIMsiString@@H@Z`
- size: `2555`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const struct IMsiString **, int)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801cc968`

## callees

- `0x180025904`
- `0x180025a18`
- `0x18003bccc`
- `0x18004295c`
- `0x180061334`
- `0x1800620e4`
- `0x180064a78`
- `0x180066074`
- `0x180068680`
- `0x180076e28`
- `0x180079dd0`
- `0x18007b894`
- `0x1800b8034`
- `0x1800cb7a0`
- `0x1800cb888`
- `0x1800cb9d8`
- `0x180195930`
- `0x1802283f0`
- `0x1802284d0`
- `0x180228574`
- `0x180228c08`
- `0x18022912c`
- `0x18025ab12`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!SetEndOfFile` at `0x1802298f2`
- `KERNEL32!SetEndOfFile` at `0x1802298f2`
- `KERNEL32!CloseHandle` at `0x180229a5a`
- `KERNEL32!CloseHandle` at `0x180229a5a`
- `KERNEL32!DeleteFileW` at `0x180229a7b`
- `KERNEL32!DeleteFileW` at `0x180229a92`
- `KERNEL32!DeleteFileW` at `0x180229a7b`
- `KERNEL32!DeleteFileW` at `0x180229a92`
- `KERNEL32!GetLastError` at `0x1802292e7`
- `KERNEL32!GetLastError` at `0x18022943d`
- `KERNEL32!GetLastError` at `0x1802295ed`
- `KERNEL32!GetLastError` at `0x180229634`
- `KERNEL32!GetLastError` at `0x1802292e7`
- `KERNEL32!GetLastError` at `0x18022943d`
- `KERNEL32!GetLastError` at `0x1802295ed`
- `KERNEL32!GetLastError` at `0x180229634`
- `KERNEL32!CreateFileW` at `0x180229587`
- `KERNEL32!CreateFileW` at `0x1802296a7`
- `KERNEL32!CreateFileW` at `0x180229587`
- `KERNEL32!CreateFileW` at `0x1802296a7`
- `KERNEL32!GetTempFileNameW` at `0x180229554`
- `KERNEL32!GetTempFileNameW` at `0x1802295e3`
- `KERNEL32!GetTempFileNameW` at `0x18022962a`
- `KERNEL32!GetTempFileNameW` at `0x180229554`
- `KERNEL32!GetTempFileNameW` at `0x1802295e3`
- `KERNEL32!GetTempFileNameW` at `0x18022962a`
- `KERNEL32!WriteFile` at `0x180229819`
- `KERNEL32!WriteFile` at `0x180229845`
- `KERNEL32!WriteFile` at `0x180229819`
- `KERNEL32!WriteFile` at `0x180229845`

## string_xrefs

- `0x180229182`: `File path is a URL. Downloading file. . .`
- `0x18022929d`: `Windows Installer`

## pseudocode

```c
__int64 __fastcall WinHttpDownloadUrlFile(unsigned __int16 *a1, const struct IMsiString **a2, int a3)
{
  unsigned int v5; // r14d
  void *v6; // r12
  void *v7; // r13
  const struct IMsiString *TempDirectory; // rdi
  const struct IMsiString *MsiDirectory; // rbx
  __int64 FileW; // r15
  DWORD LastError; // esi
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned __int64 v14; // kr00_8
  void *v15; // r12
  unsigned int v16; // eax
  __int64 v17; // rax
  char *v18; // rsi
  __int64 v19; // rax
  int v20; // ecx
  void *v21; // rax
  void *v22; // rsi
  unsigned __int16 *v23; // r12
  WCHAR *v24; // rsi
  const WCHAR *v25; // rax
  WCHAR *v26; // rsi
  const WCHAR *v27; // rax
  WCHAR *v28; // rsi
  const WCHAR *v29; // rax
  DWORD v30; // eax
  struct IMsiRecord *v31; // rax
  unsigned int v32; // esi
  void *v33; // r12
  __int64 v34; // r8
  BOOL v35; // r12d
  MsiString *v36; // rsi
  void *v37; // rax
  void *v39; // [rsp+60h] [rbp-A0h]
  LONG lDistanceToMove; // [rsp+68h] [rbp-98h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v43; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v44; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v45; // [rsp+84h] [rbp-7Ch] BYREF
  int v46; // [rsp+88h] [rbp-78h] BYREF
  void *v47; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v48; // [rsp+98h] [rbp-68h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-60h]
  __int64 v50; // [rsp+A8h] [rbp-58h] BYREF
  const struct IMsiString **v51; // [rsp+B0h] [rbp-50h] BYREF
  void *v52; // [rsp+B8h] [rbp-48h]
  void *v53; // [rsp+C0h] [rbp-40h]
  __int64 v54; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v55[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v56; // [rsp+E0h] [rbp-20h]
  int v57; // [rsp+E4h] [rbp-1Ch]
  char v58; // [rsp+E8h] [rbp-18h]
  _DWORD v59[6]; // [rsp+F0h] [rbp-10h] BYREF
  void *Src; // [rsp+108h] [rbp+8h]
  unsigned int v61; // [rsp+110h] [rbp+10h]
  unsigned __int16 v62; // [rsp+114h] [rbp+14h]
  void *v63; // [rsp+138h] [rbp+38h]
  unsigned int v64; // [rsp+140h] [rbp+40h]
  void *v65; // [rsp+148h] [rbp+48h]
  unsigned int v66; // [rsp+150h] [rbp+50h]
  _QWORD v67[2]; // [rsp+160h] [rbp+60h] BYREF
  LPWSTR lpTempFileName[3]; // [rsp+170h] [rbp+70h] BYREF

  v51 = a2;
  v48 = a1;
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      L"File path is a URL. Downloading file. . .",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  v67[1] = 0;
  v67[0] = L"*/*";
  memset_0(v59, 0, 0x68u);
  v55[0] = (__int64)CreateRecord(5u);
  v55[1] = 0;
  v56 = 0;
  v57 = a3;
  v58 = 0;
  v45 = 0;
  v43 = 0;
  v44 = 0;
  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  lDistanceToMove = 0;
  v46 = 0;
  v54 = 0;
  v50 = 0;
  CTempBuffer<unsigned short,1>::CTempBuffer<unsigned short,1>((__int64)lpTempFileName, 261);
  if ( !lpTempFileName[0] )
  {
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)lpTempFileName);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v50);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v54);
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    v5 = 14;
    goto LABEL_105;
  }
  v49 = 0;
  v47 = 0;
  v52 = 0;
  v6 = 0;
  v7 = 0;
  TempDirectory = (const struct IMsiString *)&MsiString::s_NullString;
  MsiDirectory = (const struct IMsiString *)&MsiString::s_NullString;
  FileW = -1;
  v53 = (void *)((__int64 (__fastcall *)(const wchar_t *, _QWORD, _QWORD, _QWORD, _DWORD))WINHTTP::WinHttpOpen)(
                  L"Windows Installer",
                  0,
                  0,
                  0,
                  0);
  v5 = 14;
  if ( v53 )
  {
    memset_0(v59, 0, 0x68u);
    v59[0] = 104;
    v64 = -1;
    v61 = -1;
    v66 = -1;
    if ( (unsigned int)((__int64 (__fastcall *)(unsigned __int16 *, _QWORD, _QWORD, _DWORD *))WINHTTP::WinHttpCrackUrl)(
                         a1,
                         0,
                         0,
                         v59) )
    {
      if ( !v63 )
      {
        v63 = (void *)&Default;
        v64 = 0;
      }
      if ( Src )
      {
        v12 = v61;
      }
      else
      {
        Src = (void *)&Default;
        v12 = 0;
        v61 = 0;
      }
      if ( !v65 )
      {
        v65 = (void *)&Default;
        v66 = 0;
      }
      v14 = v12 + 1;
      v13 = 2 * (v12 + 1);
      if ( !is_mul_ok(v14, 2u) )
        v13 = -1;
      v15 = (void *)operator new(v13);
      v52 = v15;
      v16 = 2 * (v64 + 1 + v66);
      if ( !is_mul_ok(v64 + 1 + v66, 2u) )
        v16 = -1;
      v17 = operator new(v16);
      v39 = (void *)v17;
      v18 = (char *)v17;
      if ( !v15 || !v17 )
      {
        v6 = (void *)v17;
        goto LABEL_80;
      }
      memcpy_0(v15, Src, 2LL * v61);
      *((_WORD *)v15 + v61) = 0;
      memcpy_0(v18, v63, 2LL * v64);
      memcpy_0(&v18[2 * v64], v65, 2LL * v66);
      *(_WORD *)&v18[2 * v66 + 2 * v64] = 0;
      v19 = ((__int64 (__fastcall *)(void *, void *, _QWORD, _QWORD))WINHTTP::WinHttpConnect)(v53, v15, v62, 0);
      v49 = v19;
      if ( !v19 )
        goto LABEL_22;
      v20 = 0;
      if ( v59[5] == 2 )
        v20 = 0x800000;
      v21 = (void *)((__int64 (__fastcall *)(__int64, _QWORD, char *, _QWORD, _QWORD, _QWORD *, int))WINHTTP::WinHttpOpenRequest)(
                      v19,
                      0,
                      v18,
                      0,
                      0,
                      v67,
                      v20);
      v47 = v21;
      v22 = v21;
      if ( !v21 )
        goto LABEL_22;
      v23 = v48;
      if ( !(unsigned int)MsiWinHttpSendRequestAndReceiveResponse(v53, v21, v48, &v43) )
        goto LABEL_22;
      if ( v43 != 200 )
      {
        LastError = 2;
        goto LABEL_23;
      }
      v46 = 4;
      if ( !(unsigned int)((__int64 (__fastcall *)(void *, __int64, _QWORD, LONG *, int *, _QWORD))WINHTTP::WinHttpQueryHeaders)(
                            v22,
                            536870917,
                            0,
                            &lDistanceToMove,
                            &v46,
                            0) )
      {
LABEL_22:
        LastError = GetLastError();
LABEL_23:
        v6 = v39;
        goto LABEL_81;
      }
      if ( g_scServerContext != 2 && !IsAdmin() )
      {
        TempDirectory = GetTempDirectory();
        (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
        v24 = lpTempFileName[0];
        v25 = (const WCHAR *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)TempDirectory + 80LL))(TempDirectory);
        if ( !GetTempFileNameW(v25, L"MSI", 0, v24) )
          goto LABEL_22;
        FileW = (__int64)CreateFileW(lpTempFileName[0], 0x40000000u, 1u, 0, 5u, 0x100000u, 0);
        goto LABEL_46;
      }
      CElevate::CElevate((CElevate *)&v43, 1);
      MsiDirectory = GetMsiDirectory();
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      v26 = lpTempFileName[0];
      v27 = (const WCHAR *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)MsiDirectory + 80LL))(MsiDirectory);
      if ( !GetTempFileNameW(v27, L"MSI", 0, v26) )
      {
        LastError = GetLastError();
        if ( LastError != 267 || (unsigned int)MsiCreateAndVerifyInstallerDirectory(0) )
          goto LABEL_41;
        v28 = lpTempFileName[0];
        v29 = (const WCHAR *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)MsiDirectory + 80LL))(MsiDirectory);
        if ( !GetTempFileNameW(v29, L"MSI", 0, v28) )
        {
          v30 = GetLastError();
LABEL_40:
          LastError = v30;
LABEL_41:
          CElevate::~CElevate((CElevate *)&v43);
          goto LABEL_23;
        }
        v45 = 0;
      }
      v31 = LockdownPath(lpTempFileName[0], 0);
      CComPointer<IMsiDatabase>::operator=(&v50, v31);
      if ( !v50 )
      {
        FileW = (__int64)CreateFileW(lpTempFileName[0], 0x40000000u, 1u, 0, 5u, 0x100000u, 0);
        CElevate::~CElevate((CElevate *)&v43);
LABEL_46:
        if ( FileW != -1 )
        {
          if ( !MsiSetFileSize((HANDLE)FileW, lDistanceToMove, &v45) )
          {
            LastError = v45;
            goto LABEL_23;
          }
          if ( g_dmDiagnosticMode )
            DebugString(
              10,
              0,
              0,
              L"Downloading %s to local file %s",
              v23,
              lpTempFileName[0],
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          if ( CMsiWinHttpProgress::BeginDownload((CMsiWinHttpProgress *)v55, lDistanceToMove) )
          {
            v32 = lDistanceToMove;
            if ( (unsigned int)lDistanceToMove >= 0x10000 )
            {
              v32 = 0x10000;
            }
            else if ( (unsigned int)lDistanceToMove < 0x400 )
            {
              v32 = 1024;
            }
            v7 = (void *)operator new(v32);
            if ( !v7 )
            {
              v6 = v39;
LABEL_80:
              LastError = 14;
              goto LABEL_81;
            }
            while ( 1 )
            {
              v33 = v47;
              v44 = 0;
              if ( !(unsigned int)((__int64 (__fastcall *)(void *, unsigned int *))WINHTTP::WinHttpQueryDataAvailable)(
                                    v47,
                                    &v44) )
                break;
              if ( !v44 )
              {
                if ( CMsiWinHttpProgress::FinishDownload((CMsiWinHttpProgress *)v55) )
                {
                  if ( !lDistanceToMove )
                    goto LABEL_77;
                  if ( g_dmDiagnosticMode )
                    DebugString(
                      10,
                      0,
                      0,
                      L"Downloaded File is %d bytes smaller then declared for URL resource %s",
                      (const unsigned __int16 *)(unsigned int)lDistanceToMove,
                      v48,
                      L"(NULL)",
                      L"(NULL)",
                      L"(NULL)",
                      L"(NULL)",
                      0,
                      0);
                  if ( SetEndOfFile((HANDLE)FileW) )
                  {
LABEL_77:
                    v36 = MsiString::MsiString((MsiString *)&v48, lpTempFileName[0]);
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v36 + 8LL))(*(_QWORD *)v36);
                    *v51 = *(const struct IMsiString **)v36;
                    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v48 + 16LL))(v48);
                    v37 = v52;
                    v5 = 0;
                    v6 = v39;
                    goto LABEL_87;
                  }
                }
                goto LABEL_22;
              }
              nNumberOfBytesToWrite = 0;
              v34 = v32;
              if ( v44 <= v32 )
                v34 = v44;
              if ( !(unsigned int)((__int64 (__fastcall *)(void *, void *, __int64, DWORD *))WINHTTP::WinHttpReadData)(
                                    v33,
                                    v7,
                                    v34,
                                    &nNumberOfBytesToWrite)
                || !CMsiWinHttpProgress::ContinueDownload((CMsiWinHttpProgress *)v55, nNumberOfBytesToWrite) )
              {
                goto LABEL_22;
              }
              NumberOfBytesWritten = 0;
              if ( g_scServerContext == 2 || IsAdmin() )
              {
                CElevate::CElevate((CElevate *)&v43, 1);
                v35 = WriteFile((HANDLE)FileW, v7, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
                CElevate::~CElevate((CElevate *)&v43);
              }
              else
              {
                v35 = WriteFile((HANDLE)FileW, v7, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
              }
              if ( !v35 || nNumberOfBytesToWrite != NumberOfBytesWritten )
                goto LABEL_22;
              if ( lDistanceToMove >= NumberOfBytesWritten )
                lDistanceToMove -= NumberOfBytesWritten;
            }
          }
        }
        goto LABEL_22;
      }
      v30 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 56LL))(v50, 2);
      goto LABEL_40;
    }
  }
  LastError = GetLastError();
LABEL_81:
  if ( g_dmDiagnosticMode )
    DebugString(
      10,
      0,
      0,
      L"Download of URL resource %s failed with last error %d",
      v48,
      (const unsigned __int16 *)LastError,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  if ( LastError != 14 )
  {
    v5 = 1602;
    if ( LastError != 1602 )
      v5 = 2;
  }
  *v51 = (const struct IMsiString *)&g_MsiStringNull;
  v37 = v52;
  if ( v52 )
LABEL_87:
    operator delete(v37);
  if ( v6 )
    operator delete(v6);
  if ( v7 )
    operator delete(v7);
  if ( v47 )
    ((void (__fastcall *)(void *))WINHTTP::WinHttpCloseHandle)(v47);
  if ( v49 )
    ((void (__fastcall *)(__int64))WINHTTP::WinHttpCloseHandle)(v49);
  if ( v53 )
    ((void (__fastcall *)(void *))WINHTTP::WinHttpCloseHandle)(v53);
  if ( FileW != -1 )
  {
    CloseHandle((HANDLE)FileW);
    if ( v5 )
    {
      if ( g_scServerContext == 2 || IsAdmin() )
      {
        CElevate::CElevate((CElevate *)&v51, 1);
        DeleteFileW(lpTempFileName[0]);
        CElevate::~CElevate((CElevate *)&v51);
      }
      else
      {
        DeleteFileW(lpTempFileName[0]);
      }
    }
  }
  CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)lpTempFileName);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v50);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v54);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
  (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)TempDirectory + 16LL))(TempDirectory);
LABEL_105:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v55);
  return v5;
}

```

## disassembly

```asm
0x18022912c  mov     [rsp-8+arg_10], rbx
0x180229131  push    rbp
0x180229132  push    rsi
0x180229133  push    rdi
0x180229134  push    r12
0x180229136  push    r13
0x180229138  push    r14
0x18022913a  push    r15
0x18022913c  lea     rbp, [rsp-90h]
0x180229144  sub     rsp, 190h
0x18022914b  mov     rax, cs:__security_cookie
0x180229152  xor     rax, rsp
0x180229155  mov     [rbp+0C0h+var_38], rax
0x18022915c  xor     r14d, r14d
0x18022915f  mov     [rbp+0C0h+var_110], rdx
0x180229163  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x18022916a  lea     rax, aNull; "(NULL)"
0x180229171  mov     ebx, r8d
0x180229174  mov     [rbp+0C0h+var_128], rcx
0x180229178  mov     rsi, rcx
0x18022917b  jz      short loc_1802291B9
0x18022917d  mov     [rsp+1C0h+var_168], r14; void *
0x180229182  lea     r9, aFilePathIsAUrl; "File path is a URL. Downloading file. ."...
0x180229189  mov     [rsp+1C0h+var_170], r14d; unsigned int
0x18022918e  xor     edx, edx; unsigned __int16
0x180229190  mov     [rsp+1C0h+var_178], rax; unsigned __int16 *
0x180229195  xor     r8d, r8d; int
0x180229198  mov     [rsp+1C0h+var_180], rax; unsigned __int16 *
0x18022919d  mov     [rsp+1C0h+var_188], rax; unsigned __int16 *
0x1802291a2  mov     [rsp+1C0h+hTemplateFile], rax; unsigned __int16 *
0x1802291a7  lea     ecx, [rdx+9]; int
0x1802291aa  mov     qword ptr [rsp+1C0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x1802291af  mov     qword ptr [rsp+1C0h+dwCreationDisposition], rax; unsigned __int16 *
0x1802291b4  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1802291b9  xor     edx, edx; Val
0x1802291bb  mov     [rbp+0C0h+var_58], r14
0x1802291bf  lea     rax, asc_1802CF930; "*/*"
0x1802291c6  lea     rcx, [rbp+0C0h+var_D0]; void *
0x1802291ca  mov     [rbp+0C0h+var_60], rax
0x1802291ce  lea     r8d, [rdx+68h]; Size
0x1802291d2  call    memset_0
0x1802291d7  mov     ecx, 5; unsigned int
0x1802291dc  call    ?CreateRecord@@YAAEAVIMsiRecord@@I@Z; CreateRecord(uint)
0x1802291e1  mov     edx, 105h
0x1802291e6  mov     [rbp+0C0h+var_F0], rax
0x1802291ea  lea     rcx, [rbp+0C0h+lpTempFileName]
0x1802291ee  mov     [rbp+0C0h+var_E8], r14
0x1802291f2  mov     [rbp+0C0h+var_E0], r14d
0x1802291f6  mov     [rbp+0C0h+var_DC], ebx
0x1802291f9  mov     [rbp+0C0h+var_D8], r14b
0x1802291fd  mov     [rbp+0C0h+var_13C], r14d
0x180229201  mov     [rsp+1C0h+var_148], r14d
0x180229206  mov     [rbp+0C0h+var_140], r14d
0x18022920a  mov     [rsp+1C0h+nNumberOfBytesToWrite], r14d
0x18022920f  mov     [rsp+1C0h+NumberOfBytesWritten], r14d
0x180229214  mov     [rsp+1C0h+lDistanceToMove], r14d
0x180229219  mov     [rbp+0C0h+var_138], r14d
0x18022921d  mov     [rbp+0C0h+var_F8], r14
0x180229221  mov     [rbp+0C0h+var_118], r14
0x180229225  call    ??0?$CTempBuffer@G$00@@QEAA@H@Z; CTempBuffer<ushort,1>::CTempBuffer<ushort,1>(int)
0x18022922a  cmp     [rbp+0C0h+lpTempFileName], r14
0x18022922e  jnz     short loc_180229296
0x180229230  lea     rcx, [rbp+0C0h+lpTempFileName]
0x180229234  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x180229239  lea     rcx, [rbp+0C0h+var_118]
0x18022923d  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180229242  lea     rcx, [rbp+0C0h+var_F8]
0x180229246  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x18022924b  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180229252  lea     rbx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180229259  mov     rcx, rbx
0x18022925c  mov     rax, [rax+10h]
0x180229260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180229265  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18022926c  mov     rcx, rbx
0x18022926f  mov     rax, [rax+10h]
0x180229273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180229278  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18022927f  mov     rcx, rbx
0x180229282  mov     rax, [rax+10h]
0x180229286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022928b  mov     r14d, 0Eh
0x180229291  jmp     loc_180229AF1
0x180229296  mov     rax, cs:?WinHttpOpen@WINHTTP@@3P6APEAXPEBGK00K@ZEA; void * (*WINHTTP::WinHttpOpen)(ushort const *,ulong,ushort const *,ushort const *,ulong)
0x18022929d  lea     rcx, aWindowsInstall_0; "Windows Installer"
0x1802292a4  xor     r9d, r9d
0x1802292a7  mov     [rbp+0C0h+var_120], r14
0x1802292ab  xor     r8d, r8d
0x1802292ae  mov     [rbp+0C0h+var_130], r14
0x1802292b2  xor     edx, edx
0x1802292b4  mov     [rbp+0C0h+var_108], r14
0x1802292b8  mov     r12, r14
0x1802292bb  mov     [rsp+1C0h+dwCreationDisposition], r14d
0x1802292c0  mov     r13, r14
0x1802292c3  lea     rdi, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1802292ca  lea     rbx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1802292d1  or      r15, 0FFFFFFFFFFFFFFFFh
0x1802292d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802292da  mov     [rbp+0C0h+var_100], rax
0x1802292de  lea     r14d, [r15+0Fh]
0x1802292e2  test    rax, rax
0x1802292e5  jnz     short loc_1802292F4
0x1802292e7  call    cs:__imp_GetLastError
0x1802292ed  mov     esi, eax
0x1802292ef  jmp     loc_180229958
0x1802292f4  xor     edx, edx; Val
0x1802292f6  lea     rcx, [rbp+0C0h+var_D0]; void *
0x1802292fa  lea     r8d, [rdx+68h]; Size
0x1802292fe  call    memset_0
0x180229303  or      eax, 0FFFFFFFFh
0x180229306  mov     [rbp+0C0h+var_D0], 68h ; 'h'
0x18022930d  mov     [rbp+0C0h+var_80], eax
0x180229310  lea     r9, [rbp+0C0h+var_D0]
0x180229314  mov     [rbp+0C0h+var_B0], eax
0x180229317  xor     r8d, r8d
0x18022931a  mov     [rbp+0C0h+var_70], eax
0x18022931d  xor     edx, edx
0x18022931f  mov     rax, cs:?WinHttpCrackUrl@WINHTTP@@3P6AHPEBGKKPEAU_WINHTTP_URL_COMPONENTS@@@ZEA; int (*WINHTTP::WinHttpCrackUrl)(ushort const *,ulong,ulong,_WINHTTP_URL_COMPONENTS *)
0x180229326  mov     rcx, rsi
0x180229329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022932e  xor     ecx, ecx
0x180229330  test    eax, eax
0x180229332  jz      short loc_1802292E7
0x180229334  lea     rdx, Default
0x18022933b  cmp     [rbp+0C0h+var_88], rcx
0x18022933f  jnz     short loc_180229348
0x180229341  mov     [rbp+0C0h+var_88], rdx
0x180229345  mov     [rbp+0C0h+var_80], ecx
0x180229348  cmp     [rbp+0C0h+Src], rcx
0x18022934c  jnz     short loc_180229359
0x18022934e  mov     [rbp+0C0h+Src], rdx
0x180229352  mov     eax, ecx
0x180229354  mov     [rbp+0C0h+var_B0], ecx
0x180229357  jmp     short loc_18022935C
0x180229359  mov     eax, [rbp+0C0h+var_B0]
0x18022935c  cmp     [rbp+0C0h+var_78], rcx
0x180229360  jnz     short loc_180229369
0x180229362  mov     [rbp+0C0h+var_78], rdx
0x180229366  mov     [rbp+0C0h+var_70], ecx
0x180229369  lea     ecx, [rax+1]
0x18022936c  mov     esi, 2
0x180229371  mov     eax, esi
0x180229373  mul     rcx
0x180229376  lea     rcx, [rsi-3]
0x18022937a  cmovb   rax, rcx
0x18022937e  mov     rcx, rax; unsigned __int64
0x180229381  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180229386  mov     ecx, [rbp+0C0h+var_70]
0x180229389  mov     r12, rax
0x18022938c  mov     edx, [rbp+0C0h+var_80]
0x18022938f  mov     [rbp+0C0h+var_108], rax
0x180229393  inc     edx
0x180229395  add     ecx, edx
0x180229397  mov     eax, esi
0x180229399  mul     rcx
0x18022939c  lea     rcx, [rsi-3]
0x1802293a0  cmovb   rax, rcx
0x1802293a4  mov     rcx, rax; unsigned __int64
0x1802293a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802293ac  mov     [rsp+1C0h+var_160], rax
0x1802293b1  mov     rsi, rax
0x1802293b4  test    r12, r12
0x1802293b7  jz      loc_180229952
0x1802293bd  test    rax, rax
0x1802293c0  jz      loc_180229952
0x1802293c6  mov     r8d, [rbp+0C0h+var_B0]
0x1802293ca  mov     rcx, r12; void *
0x1802293cd  mov     rdx, [rbp+0C0h+Src]; Src
0x1802293d1  add     r8, r8; Size
0x1802293d4  call    memcpy_0
0x1802293d9  mov     edx, [rbp+0C0h+var_B0]
0x1802293dc  xor     ecx, ecx
0x1802293de  mov     [r12+rdx*2], cx
0x1802293e3  mov     rcx, rsi; void *
0x1802293e6  mov     r8d, [rbp+0C0h+var_80]
0x1802293ea  mov     rdx, [rbp+0C0h+var_88]; Src
0x1802293ee  add     r8, r8; Size
0x1802293f1  call    memcpy_0
0x1802293f6  mov     eax, [rbp+0C0h+var_80]
0x1802293f9  mov     r8d, [rbp+0C0h+var_70]
0x1802293fd  mov     rdx, [rbp+0C0h+var_78]; Src
0x180229401  add     r8, r8; Size
0x180229404  lea     rcx, [rsi+rax*2]; void *
0x180229408  call    memcpy_0
0x18022940d  mov     ecx, [rbp+0C0h+var_80]
0x180229410  xor     eax, eax
0x180229412  add     ecx, [rbp+0C0h+var_70]
0x180229415  xor     r9d, r9d
0x180229418  mov     rdx, r12
0x18022941b  mov     [rsi+rcx*2], ax
0x18022941f  movzx   r8d, [rbp+0C0h+var_AC]
0x180229424  mov     rcx, [rbp+0C0h+var_100]
0x180229428  mov     rax, cs:?WinHttpConnect@WINHTTP@@3P6APEAXPEAXPEBGGK@ZEA; void * (*WINHTTP::WinHttpConnect)(void *,ushort const *,ushort,ulong)
0x18022942f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180229434  mov     [rbp+0C0h+var_120], rax
0x180229438  test    rax, rax
0x18022943b  jnz     short loc_18022944F
0x18022943d  call    cs:__imp_GetLastError
0x180229443  mov     esi, eax
0x180229445  mov     r12, [rsp+1C0h+var_160]
0x18022944a  jmp     loc_180229958
0x18022944f  xor     ecx, ecx
0x180229451  mov     edx, 800000h
0x180229456  cmp     [rbp+0C0h+var_BC], 2
0x18022945a  mov     r8, rsi
0x18022945d  cmovz   ecx, edx
0x180229460  xor     r9d, r9d
0x180229463  mov     dword ptr [rsp+1C0h+hTemplateFile], ecx
0x180229467  xor     edx, edx
0x180229469  lea     rcx, [rbp+0C0h+var_60]
0x18022946d  mov     qword ptr [rsp+1C0h+dwFlagsAndAttributes], rcx
0x180229472  mov     rcx, rax
0x180229475  mov     rax, cs:?WinHttpOpenRequest@WINHTTP@@3P6APEAXPEAXPEBG111PEAPEBGK@ZEA; void * (*WINHTTP::WinHttpOpenRequest)(void *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const * *,ulong)
0x18022947c  mov     qword ptr [rsp+1C0h+dwCreationDisposition], r13
0x180229481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180229486  mov     [rbp+0C0h+var_130], rax
0x18022948a  mov     rsi, rax
0x18022948d  test    rax, rax
0x180229490  jz      short loc_18022943D
0x180229492  mov     r12, [rbp+0C0h+var_128]
0x180229496  lea     r9, [rsp+1C0h+var_148]; unsigned int *
0x18022949b  mov     rcx, [rbp+0C0h+var_100]; void *
0x18022949f  mov     r8, r12; unsigned __int16 *
0x1802294a2  mov     rdx, rax; void *
0x1802294a5  call    ?MsiWinHttpSendRequestAndReceiveResponse@@YAHPEAX0PEBGPEAK@Z; MsiWinHttpSendRequestAndReceiveResponse(void *,void *,ushort const *,ulong *)
0x1802294aa  test    eax, eax
0x1802294ac  jz      short loc_18022943D
0x1802294ae  cmp     [rsp+1C0h+var_148], 0C8h
0x1802294b6  jz      short loc_1802294BF
0x1802294b8  mov     esi, 2
0x1802294bd  jmp     short loc_180229445
0x1802294bf  lea     rax, [rbp+0C0h+var_138]
0x1802294c3  mov     qword ptr [rsp+1C0h+dwFlagsAndAttributes], r13
0x1802294c8  mov     qword ptr [rsp+1C0h+dwCreationDisposition], rax
0x1802294cd  lea     r9, [rsp+1C0h+lDistanceToMove]
0x1802294d2  mov     rax, cs:?WinHttpQueryHeaders@WINHTTP@@3P6AHPEAXKPEBG0PEAK2@ZEA; int (*WINHTTP::WinHttpQueryHeaders)(void *,ulong,ushort const *,void *,ulong *,ulong *)
0x1802294d9  xor     r8d, r8d
0x1802294dc  mov     edx, 20000005h
0x1802294e1  mov     [rbp+0C0h+var_138], 4
0x1802294e8  mov     rcx, rsi
0x1802294eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802294f0  test    eax, eax
0x1802294f2  jz      loc_18022943D
0x1802294f8  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x1802294ff  jz      loc_180229595
0x180229505  call    ?IsAdmin@@YA_NXZ; IsAdmin(void)
0x18022950a  test    al, al
0x18022950c  jnz     loc_180229595
0x180229512  call    ?GetTempDirectory@@YAAEBVIMsiString@@XZ; GetTempDirectory(void)
0x180229517  mov     rdi, rax
0x18022951a  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180229521  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180229528  mov     rax, [rax+10h]
0x18022952c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180229531  mov     rax, [rdi]
0x180229534  mov     rcx, rdi
0x180229537  mov     rsi, [rbp+0C0h+lpTempFileName]
0x18022953b  mov     rax, [rax+50h]
0x18022953f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180229544  mov     r9, rsi; lpTempFileName
0x180229547  lea     rdx, PrefixString; "MSI"
0x18022954e  xor     r8d, r8d; uUnique
0x180229551  mov     rcx, rax; lpPathName
0x180229554  call    cs:__imp_GetTempFileNameW
0x18022955a  test    eax, eax
0x18022955c  jz      loc_18022943D
0x180229562  mov     rcx, [rbp+0C0h+lpTempFileName]; lpFileName
0x180229566  xor     r9d, r9d; lpSecurityAttributes
0x180229569  mov     [rsp+1C0h+hTemplateFile], r13; hTemplateFile
0x18022956e  mov     edx, 40000000h; dwDesiredAccess
0x180229573  mov     [rsp+1C0h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x18022957b  mov     [rsp+1C0h+dwCreationDisposition], 5; dwCreationDisposition
0x180229583  lea     r8d, [r9+1]; dwShareMode
0x180229587  call    cs:__imp_CreateFileW
0x18022958d  mov     r15, rax
0x180229590  jmp     loc_1802296BA
0x180229595  mov     dl, 1; bool
0x180229597  lea     rcx, [rsp+1C0h+var_148]; this
0x18022959c  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x1802295a1  call    ?GetMsiDirectory@@YAAEBVIMsiString@@XZ; GetMsiDirectory(void)
0x1802295a6  mov     rbx, rax
0x1802295a9  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1802295b0  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1802295b7  mov     rax, [rax+10h]
0x1802295bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802295c0  mov     rax, [rbx]
0x1802295c3  mov     rcx, rbx
0x1802295c6  mov     rsi, [rbp+0C0h+lpTempFileName]
0x1802295ca  mov     rax, [rax+50h]
0x1802295ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802295d3  mov     r9, rsi; lpTempFileName
0x1802295d6  lea     rdx, PrefixString; "MSI"
0x1802295dd  xor     r8d, r8d; uUnique
0x1802295e0  mov     rcx, rax; lpPathName
0x1802295e3  call    cs:__imp_GetTempFileNameW
0x1802295e9  test    eax, eax
0x1802295eb  jnz     short loc_18022964F
0x1802295ed  call    cs:__imp_GetLastError
0x1802295f3  mov     esi, eax
0x1802295f5  cmp     eax, 10Bh
  ... truncated ...
```
