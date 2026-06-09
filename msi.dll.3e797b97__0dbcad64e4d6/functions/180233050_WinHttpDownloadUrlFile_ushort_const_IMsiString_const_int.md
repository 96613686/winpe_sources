# WinHttpDownloadUrlFile(ushort const *,IMsiString const * &,int)

- ea: `0x180233050`
- end: `0x180233aa6`
- name: `?WinHttpDownloadUrlFile@@YAKPEBGAEAPEBVIMsiString@@H@Z`
- size: `2646`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const struct IMsiString **, int)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801d52c8`

## callees

- `0x180005af8`
- `0x18000c4bc`
- `0x180014528`
- `0x180014e38`
- `0x180018ee0`
- `0x180019cc0`
- `0x18001f57c`
- `0x18002e870`
- `0x180056574`
- `0x1800586a0`
- `0x180058790`
- `0x180067fec`
- `0x180077470`
- `0x1800798e4`
- `0x18008c93c`
- `0x1800c08f8`
- `0x18019c5d0`
- `0x18023225c`
- `0x180232348`
- `0x1802323f4`
- `0x180232ae8`
- `0x180233050`
- `0x1802651d2`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!SetEndOfFile` at `0x180233858`
- `KERNEL32!SetEndOfFile` at `0x180233858`
- `KERNEL32!CloseHandle` at `0x1802339c6`
- `KERNEL32!CloseHandle` at `0x1802339c6`
- `KERNEL32!DeleteFileW` at `0x1802339ed`
- `KERNEL32!DeleteFileW` at `0x180233a0a`
- `KERNEL32!DeleteFileW` at `0x1802339ed`
- `KERNEL32!DeleteFileW` at `0x180233a0a`
- `KERNEL32!GetLastError` at `0x18023320b`
- `KERNEL32!GetLastError` at `0x180233367`
- `KERNEL32!GetLastError` at `0x18023352f`
- `KERNEL32!GetLastError` at `0x180233582`
- `KERNEL32!GetLastError` at `0x18023320b`
- `KERNEL32!GetLastError` at `0x180233367`
- `KERNEL32!GetLastError` at `0x18023352f`
- `KERNEL32!GetLastError` at `0x180233582`
- `KERNEL32!CreateFileW` at `0x1802334bd`
- `KERNEL32!CreateFileW` at `0x1802335fb`
- `KERNEL32!CreateFileW` at `0x1802334bd`
- `KERNEL32!CreateFileW` at `0x1802335fb`
- `KERNEL32!GetTempFileNameW` at `0x180233484`
- `KERNEL32!GetTempFileNameW` at `0x18023351f`
- `KERNEL32!GetTempFileNameW` at `0x180233572`
- `KERNEL32!GetTempFileNameW` at `0x180233484`
- `KERNEL32!GetTempFileNameW` at `0x18023351f`
- `KERNEL32!GetTempFileNameW` at `0x180233572`
- `KERNEL32!WriteFile` at `0x180233773`
- `KERNEL32!WriteFile` at `0x1802337a5`
- `KERNEL32!WriteFile` at `0x180233773`
- `KERNEL32!WriteFile` at `0x1802337a5`

## string_xrefs

- `0x1802330a6`: `File path is a URL. Downloading file. . .`
- `0x1802331c1`: `Windows Installer`

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
  void *v13; // r12
  char *v14; // rax
  char *v15; // rsi
  __int64 v16; // rax
  int v17; // ecx
  void *v18; // rax
  void *v19; // rsi
  unsigned __int16 *v20; // r12
  WCHAR *v21; // rsi
  const WCHAR *v22; // rax
  WCHAR *v23; // rsi
  const WCHAR *v24; // rax
  WCHAR *v25; // rsi
  const WCHAR *v26; // rax
  DWORD v27; // eax
  struct IMsiRecord *v28; // rax
  unsigned int v29; // esi
  void *v30; // r12
  __int64 v31; // r8
  BOOL v32; // r12d
  MsiString *v33; // rsi
  void *v34; // rax
  void *v36; // [rsp+60h] [rbp-A0h]
  LONG lDistanceToMove; // [rsp+68h] [rbp-98h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v40; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v41; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v42; // [rsp+84h] [rbp-7Ch] BYREF
  int v43; // [rsp+88h] [rbp-78h] BYREF
  void *v44; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v45; // [rsp+98h] [rbp-68h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-60h]
  __int64 v47; // [rsp+A8h] [rbp-58h] BYREF
  const struct IMsiString **v48; // [rsp+B0h] [rbp-50h] BYREF
  void *v49; // [rsp+B8h] [rbp-48h]
  void *v50; // [rsp+C0h] [rbp-40h]
  __int64 v51; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v52[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v53; // [rsp+E0h] [rbp-20h]
  int v54; // [rsp+E4h] [rbp-1Ch]
  char v55; // [rsp+E8h] [rbp-18h]
  _DWORD v56[6]; // [rsp+F0h] [rbp-10h] BYREF
  void *Src; // [rsp+108h] [rbp+8h]
  unsigned int v58; // [rsp+110h] [rbp+10h]
  unsigned __int16 v59; // [rsp+114h] [rbp+14h]
  void *v60; // [rsp+138h] [rbp+38h]
  unsigned int v61; // [rsp+140h] [rbp+40h]
  void *v62; // [rsp+148h] [rbp+48h]
  unsigned int v63; // [rsp+150h] [rbp+50h]
  _QWORD v64[2]; // [rsp+160h] [rbp+60h] BYREF
  LPWSTR lpTempFileName[3]; // [rsp+170h] [rbp+70h] BYREF

  v48 = a2;
  v45 = a1;
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
  v64[1] = 0;
  v64[0] = L"*/*";
  memset_0(v56, 0, 0x68u);
  v52[0] = CreateRecord(5u);
  v52[1] = 0;
  v53 = 0;
  v54 = a3;
  v55 = 0;
  v42 = 0;
  v40 = 0;
  v41 = 0;
  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  lDistanceToMove = 0;
  v43 = 0;
  v51 = 0;
  v47 = 0;
  CTempBuffer<unsigned short,1>::CTempBuffer<unsigned short,1>(lpTempFileName, 261);
  if ( !lpTempFileName[0] )
  {
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(lpTempFileName);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v47);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v51);
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    v5 = 14;
    goto LABEL_101;
  }
  v46 = 0;
  v44 = 0;
  v49 = 0;
  v6 = 0;
  v7 = 0;
  TempDirectory = (const struct IMsiString *)&MsiString::s_NullString;
  MsiDirectory = (const struct IMsiString *)&MsiString::s_NullString;
  FileW = -1;
  v50 = (void *)((__int64 (__fastcall *)(const wchar_t *, _QWORD, _QWORD, _QWORD, _DWORD))WINHTTP::WinHttpOpen)(
                  L"Windows Installer",
                  0,
                  0,
                  0,
                  0);
  v5 = 14;
  if ( v50 )
  {
    memset_0(v56, 0, 0x68u);
    v56[0] = 104;
    v61 = -1;
    v58 = -1;
    v63 = -1;
    if ( (unsigned int)((__int64 (__fastcall *)(unsigned __int16 *, _QWORD, _QWORD, _DWORD *))WINHTTP::WinHttpCrackUrl)(
                         a1,
                         0,
                         0,
                         v56) )
    {
      if ( !v60 )
      {
        v60 = (void *)&Default;
        v61 = 0;
      }
      if ( Src )
      {
        v12 = v58;
      }
      else
      {
        Src = (void *)&Default;
        v12 = 0;
        v58 = 0;
      }
      if ( !v62 )
      {
        v62 = (void *)&Default;
        v63 = 0;
      }
      v13 = operator new(saturated_mul(v12 + 1, 2u));
      v49 = v13;
      v14 = (char *)operator new(saturated_mul(v61 + 1 + v63, 2u));
      v36 = v14;
      v15 = v14;
      if ( !v13 || !v14 )
      {
        v6 = v14;
        goto LABEL_76;
      }
      memcpy_0(v13, Src, 2LL * v58);
      *((_WORD *)v13 + v58) = 0;
      memcpy_0(v15, v60, 2LL * v61);
      memcpy_0(&v15[2 * v61], v62, 2LL * v63);
      *(_WORD *)&v15[2 * v63 + 2 * v61] = 0;
      v16 = ((__int64 (__fastcall *)(void *, void *, _QWORD, _QWORD))WINHTTP::WinHttpConnect)(v50, v13, v59, 0);
      v46 = v16;
      if ( !v16 )
        goto LABEL_18;
      v17 = 0;
      if ( v56[5] == 2 )
        v17 = 0x800000;
      v18 = (void *)((__int64 (__fastcall *)(__int64, _QWORD, char *, _QWORD, _QWORD, _QWORD *, int))WINHTTP::WinHttpOpenRequest)(
                      v16,
                      0,
                      v15,
                      0,
                      0,
                      v64,
                      v17);
      v44 = v18;
      v19 = v18;
      if ( !v18 )
        goto LABEL_18;
      v20 = v45;
      if ( !(unsigned int)MsiWinHttpSendRequestAndReceiveResponse(v50, v18, v45, &v40) )
        goto LABEL_18;
      if ( v40 != 200 )
      {
        LastError = 2;
        goto LABEL_19;
      }
      v43 = 4;
      if ( !(unsigned int)((__int64 (__fastcall *)(void *, __int64, _QWORD, LONG *, int *, _QWORD))WINHTTP::WinHttpQueryHeaders)(
                            v19,
                            536870917,
                            0,
                            &lDistanceToMove,
                            &v43,
                            0) )
      {
LABEL_18:
        LastError = GetLastError();
LABEL_19:
        v6 = v36;
        goto LABEL_77;
      }
      if ( g_scServerContext != 2 && !IsAdmin() )
      {
        TempDirectory = GetTempDirectory();
        (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
        v21 = lpTempFileName[0];
        v22 = (const WCHAR *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)TempDirectory + 80LL))(TempDirectory);
        if ( !GetTempFileNameW(v22, L"MSI", 0, v21) )
          goto LABEL_18;
        FileW = (__int64)CreateFileW(lpTempFileName[0], 0x40000000u, 1u, 0, 5u, 0x100000u, 0);
        goto LABEL_42;
      }
      CElevate::CElevate((CElevate *)&v40, 1);
      MsiDirectory = GetMsiDirectory();
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      v23 = lpTempFileName[0];
      v24 = (const WCHAR *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)MsiDirectory + 80LL))(MsiDirectory);
      if ( !GetTempFileNameW(v24, L"MSI", 0, v23) )
      {
        LastError = GetLastError();
        if ( LastError != 267 || (unsigned int)MsiCreateAndVerifyInstallerDirectory(0) )
          goto LABEL_37;
        v25 = lpTempFileName[0];
        v26 = (const WCHAR *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)MsiDirectory + 80LL))(MsiDirectory);
        if ( !GetTempFileNameW(v26, L"MSI", 0, v25) )
        {
          v27 = GetLastError();
LABEL_36:
          LastError = v27;
LABEL_37:
          CElevate::~CElevate((CElevate *)&v40);
          goto LABEL_19;
        }
        v42 = 0;
      }
      v28 = LockdownPath(lpTempFileName[0], 0);
      CComPointer<IMsiDatabase>::operator=(&v47, v28);
      if ( !v47 )
      {
        FileW = (__int64)CreateFileW(lpTempFileName[0], 0x40000000u, 1u, 0, 5u, 0x100000u, 0);
        CElevate::~CElevate((CElevate *)&v40);
LABEL_42:
        if ( FileW != -1 )
        {
          if ( !MsiSetFileSize((HANDLE)FileW, lDistanceToMove, &v42) )
          {
            LastError = v42;
            goto LABEL_19;
          }
          if ( g_dmDiagnosticMode )
            DebugString(
              10,
              0,
              0,
              L"Downloading %s to local file %s",
              v20,
              lpTempFileName[0],
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          if ( CMsiWinHttpProgress::BeginDownload((CMsiWinHttpProgress *)v52, lDistanceToMove) )
          {
            v29 = lDistanceToMove;
            if ( (unsigned int)lDistanceToMove >= 0x10000 )
            {
              v29 = 0x10000;
            }
            else if ( (unsigned int)lDistanceToMove < 0x400 )
            {
              v29 = 1024;
            }
            v7 = operator new(v29);
            if ( !v7 )
            {
              v6 = v36;
LABEL_76:
              LastError = 14;
              goto LABEL_77;
            }
            while ( 1 )
            {
              v30 = v44;
              v41 = 0;
              if ( !(unsigned int)((__int64 (__fastcall *)(void *, unsigned int *))WINHTTP::WinHttpQueryDataAvailable)(
                                    v44,
                                    &v41) )
                break;
              if ( !v41 )
              {
                if ( CMsiWinHttpProgress::FinishDownload((CMsiWinHttpProgress *)v52) )
                {
                  if ( !lDistanceToMove )
                    goto LABEL_73;
                  if ( g_dmDiagnosticMode )
                    DebugString(
                      10,
                      0,
                      0,
                      L"Downloaded File is %d bytes smaller then declared for URL resource %s",
                      (const unsigned __int16 *)(unsigned int)lDistanceToMove,
                      v45,
                      L"(NULL)",
                      L"(NULL)",
                      L"(NULL)",
                      L"(NULL)",
                      0,
                      0);
                  if ( SetEndOfFile((HANDLE)FileW) )
                  {
LABEL_73:
                    v33 = MsiString::MsiString((MsiString *)&v45, lpTempFileName[0]);
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v33 + 8LL))(*(_QWORD *)v33);
                    *v48 = *(const struct IMsiString **)v33;
                    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v45 + 16LL))(v45);
                    v34 = v49;
                    v5 = 0;
                    v6 = v36;
                    goto LABEL_83;
                  }
                }
                goto LABEL_18;
              }
              nNumberOfBytesToWrite = 0;
              v31 = v29;
              if ( v41 <= v29 )
                v31 = v41;
              if ( !(unsigned int)((__int64 (__fastcall *)(void *, void *, __int64, DWORD *))WINHTTP::WinHttpReadData)(
                                    v30,
                                    v7,
                                    v31,
                                    &nNumberOfBytesToWrite)
                || !CMsiWinHttpProgress::ContinueDownload((CMsiWinHttpProgress *)v52, nNumberOfBytesToWrite) )
              {
                goto LABEL_18;
              }
              NumberOfBytesWritten = 0;
              if ( g_scServerContext == 2 || IsAdmin() )
              {
                CElevate::CElevate((CElevate *)&v40, 1);
                v32 = WriteFile((HANDLE)FileW, v7, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
                CElevate::~CElevate((CElevate *)&v40);
              }
              else
              {
                v32 = WriteFile((HANDLE)FileW, v7, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
              }
              if ( !v32 || nNumberOfBytesToWrite != NumberOfBytesWritten )
                goto LABEL_18;
              if ( lDistanceToMove >= NumberOfBytesWritten )
                lDistanceToMove -= NumberOfBytesWritten;
            }
          }
        }
        goto LABEL_18;
      }
      v27 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v47 + 56LL))(v47, 2);
      goto LABEL_36;
    }
  }
  LastError = GetLastError();
LABEL_77:
  if ( g_dmDiagnosticMode )
    DebugString(
      10,
      0,
      0,
      L"Download of URL resource %s failed with last error %d",
      v45,
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
  *v48 = (const struct IMsiString *)&g_MsiStringNull;
  v34 = v49;
  if ( v49 )
LABEL_83:
    operator delete(v34);
  if ( v6 )
    operator delete(v6);
  if ( v7 )
    operator delete(v7);
  if ( v44 )
    ((void (__fastcall *)(void *))WINHTTP::WinHttpCloseHandle)(v44);
  if ( v46 )
    ((void (__fastcall *)(__int64))WINHTTP::WinHttpCloseHandle)(v46);
  if ( v50 )
    ((void (__fastcall *)(void *))WINHTTP::WinHttpCloseHandle)(v50);
  if ( FileW != -1 )
  {
    CloseHandle((HANDLE)FileW);
    if ( v5 )
    {
      if ( g_scServerContext == 2 || IsAdmin() )
      {
        CElevate::CElevate((CElevate *)&v48, 1);
        DeleteFileW(lpTempFileName[0]);
        CElevate::~CElevate((CElevate *)&v48);
      }
      else
      {
        DeleteFileW(lpTempFileName[0]);
      }
    }
  }
  CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(lpTempFileName);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v47);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v51);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
  (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)TempDirectory + 16LL))(TempDirectory);
LABEL_101:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v52);
  return v5;
}

```

## disassembly

```asm
0x180233050  mov     [rsp-8+arg_10], rbx
0x180233055  push    rbp
0x180233056  push    rsi
0x180233057  push    rdi
0x180233058  push    r12
0x18023305a  push    r13
0x18023305c  push    r14
0x18023305e  push    r15
0x180233060  lea     rbp, [rsp-90h]
0x180233068  sub     rsp, 190h
0x18023306f  mov     rax, cs:__security_cookie
0x180233076  xor     rax, rsp
0x180233079  mov     [rbp+0C0h+var_38], rax
0x180233080  xor     r14d, r14d
0x180233083  mov     [rbp+0C0h+var_110], rdx
0x180233087  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x18023308e  lea     rax, aNull; "(NULL)"
0x180233095  mov     ebx, r8d
0x180233098  mov     [rbp+0C0h+var_128], rcx
0x18023309c  mov     rsi, rcx
0x18023309f  jz      short loc_1802330DD
0x1802330a1  mov     [rsp+1C0h+var_168], r14; void *
0x1802330a6  lea     r9, aFilePathIsAUrl; "File path is a URL. Downloading file. ."...
0x1802330ad  mov     [rsp+1C0h+var_170], r14d; unsigned int
0x1802330b2  xor     edx, edx; unsigned __int16
0x1802330b4  mov     [rsp+1C0h+var_178], rax; unsigned __int16 *
0x1802330b9  xor     r8d, r8d; int
0x1802330bc  mov     [rsp+1C0h+var_180], rax; unsigned __int16 *
0x1802330c1  mov     [rsp+1C0h+var_188], rax; unsigned __int16 *
0x1802330c6  mov     [rsp+1C0h+hTemplateFile], rax; unsigned __int16 *
0x1802330cb  lea     ecx, [rdx+9]; int
0x1802330ce  mov     qword ptr [rsp+1C0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x1802330d3  mov     qword ptr [rsp+1C0h+dwCreationDisposition], rax; unsigned __int16 *
0x1802330d8  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1802330dd  xor     edx, edx; Val
0x1802330df  mov     [rbp+0C0h+var_58], r14
0x1802330e3  lea     rax, asc_1802D9860; "*/*"
0x1802330ea  lea     rcx, [rbp+0C0h+var_D0]; void *
0x1802330ee  mov     [rbp+0C0h+var_60], rax
0x1802330f2  lea     r8d, [rdx+68h]; Size
0x1802330f6  call    memset_0
0x1802330fb  mov     ecx, 5; unsigned int
0x180233100  call    ?CreateRecord@@YAAEAVIMsiRecord@@I@Z; CreateRecord(uint)
0x180233105  mov     edx, 105h
0x18023310a  mov     [rbp+0C0h+var_F0], rax
0x18023310e  lea     rcx, [rbp+0C0h+lpTempFileName]
0x180233112  mov     [rbp+0C0h+var_E8], r14
0x180233116  mov     [rbp+0C0h+var_E0], r14d
0x18023311a  mov     [rbp+0C0h+var_DC], ebx
0x18023311d  mov     [rbp+0C0h+var_D8], r14b
0x180233121  mov     [rbp+0C0h+var_13C], r14d
0x180233125  mov     [rsp+1C0h+var_148], r14d
0x18023312a  mov     [rbp+0C0h+var_140], r14d
0x18023312e  mov     [rsp+1C0h+nNumberOfBytesToWrite], r14d
0x180233133  mov     [rsp+1C0h+NumberOfBytesWritten], r14d
0x180233138  mov     [rsp+1C0h+lDistanceToMove], r14d
0x18023313d  mov     [rbp+0C0h+var_138], r14d
0x180233141  mov     [rbp+0C0h+var_F8], r14
0x180233145  mov     [rbp+0C0h+var_118], r14
0x180233149  call    ??0?$CTempBuffer@G$00@@QEAA@H@Z; CTempBuffer<ushort,1>::CTempBuffer<ushort,1>(int)
0x18023314e  cmp     [rbp+0C0h+lpTempFileName], r14
0x180233152  jnz     short loc_1802331BA
0x180233154  lea     rcx, [rbp+0C0h+lpTempFileName]
0x180233158  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x18023315d  lea     rcx, [rbp+0C0h+var_118]
0x180233161  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180233166  lea     rcx, [rbp+0C0h+var_F8]
0x18023316a  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x18023316f  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180233176  lea     rbx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18023317d  mov     rcx, rbx
0x180233180  mov     rax, [rax+10h]
0x180233184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180233189  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180233190  mov     rcx, rbx
0x180233193  mov     rax, [rax+10h]
0x180233197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023319c  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1802331a3  mov     rcx, rbx
0x1802331a6  mov     rax, [rax+10h]
0x1802331aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802331af  mov     r14d, 0Eh
0x1802331b5  jmp     loc_180233A6F
0x1802331ba  mov     rax, cs:?WinHttpOpen@WINHTTP@@3P6APEAXPEBGK00K@ZEA; void * (*WINHTTP::WinHttpOpen)(ushort const *,ulong,ushort const *,ushort const *,ulong)
0x1802331c1  lea     rcx, aWindowsInstall_0; "Windows Installer"
0x1802331c8  xor     r9d, r9d
0x1802331cb  mov     [rbp+0C0h+var_120], r14
0x1802331cf  xor     r8d, r8d
0x1802331d2  mov     [rbp+0C0h+var_130], r14
0x1802331d6  xor     edx, edx
0x1802331d8  mov     [rbp+0C0h+var_108], r14
0x1802331dc  mov     r12, r14
0x1802331df  mov     [rsp+1C0h+dwCreationDisposition], r14d
0x1802331e4  mov     r13, r14
0x1802331e7  lea     rdi, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1802331ee  lea     rbx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1802331f5  or      r15, 0FFFFFFFFFFFFFFFFh
0x1802331f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802331fe  mov     [rbp+0C0h+var_100], rax
0x180233202  lea     r14d, [r15+0Fh]
0x180233206  test    rax, rax
0x180233209  jnz     short loc_18023321E
0x18023320b  call    cs:__imp_GetLastError
0x180233212  nop     dword ptr [rax+rax+00h]
0x180233217  mov     esi, eax
0x180233219  jmp     loc_1802338C4
0x18023321e  xor     edx, edx; Val
0x180233220  lea     rcx, [rbp+0C0h+var_D0]; void *
0x180233224  lea     r8d, [rdx+68h]; Size
0x180233228  call    memset_0
0x18023322d  or      eax, 0FFFFFFFFh
0x180233230  mov     [rbp+0C0h+var_D0], 68h ; 'h'
0x180233237  mov     [rbp+0C0h+var_80], eax
0x18023323a  lea     r9, [rbp+0C0h+var_D0]
0x18023323e  mov     [rbp+0C0h+var_B0], eax
0x180233241  xor     r8d, r8d
0x180233244  mov     [rbp+0C0h+var_70], eax
0x180233247  xor     edx, edx
0x180233249  mov     rax, cs:?WinHttpCrackUrl@WINHTTP@@3P6AHPEBGKKPEAU_WINHTTP_URL_COMPONENTS@@@ZEA; int (*WINHTTP::WinHttpCrackUrl)(ushort const *,ulong,ulong,_WINHTTP_URL_COMPONENTS *)
0x180233250  mov     rcx, rsi
0x180233253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180233258  xor     ecx, ecx
0x18023325a  test    eax, eax
0x18023325c  jz      short loc_18023320B
0x18023325e  lea     rdx, Default
0x180233265  cmp     [rbp+0C0h+var_88], rcx
0x180233269  jnz     short loc_180233272
0x18023326b  mov     [rbp+0C0h+var_88], rdx
0x18023326f  mov     [rbp+0C0h+var_80], ecx
0x180233272  cmp     [rbp+0C0h+Src], rcx
0x180233276  jnz     short loc_180233283
0x180233278  mov     [rbp+0C0h+Src], rdx
0x18023327c  mov     eax, ecx
0x18023327e  mov     [rbp+0C0h+var_B0], ecx
0x180233281  jmp     short loc_180233286
0x180233283  mov     eax, [rbp+0C0h+var_B0]
0x180233286  cmp     [rbp+0C0h+var_78], rcx
0x18023328a  jnz     short loc_180233293
0x18023328c  mov     [rbp+0C0h+var_78], rdx
0x180233290  mov     [rbp+0C0h+var_70], ecx
0x180233293  lea     ecx, [rax+1]
0x180233296  mov     esi, 2
0x18023329b  mov     eax, esi
0x18023329d  mul     rcx
0x1802332a0  lea     rcx, [rsi-3]
0x1802332a4  cmovb   rax, rcx
0x1802332a8  mov     rcx, rax; unsigned __int64
0x1802332ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802332b0  mov     ecx, [rbp+0C0h+var_70]
0x1802332b3  mov     r12, rax
0x1802332b6  mov     edx, [rbp+0C0h+var_80]
0x1802332b9  mov     [rbp+0C0h+var_108], rax
0x1802332bd  inc     edx
0x1802332bf  add     ecx, edx
0x1802332c1  mov     eax, esi
0x1802332c3  mul     rcx
0x1802332c6  lea     rcx, [rsi-3]
0x1802332ca  cmovb   rax, rcx
0x1802332ce  mov     rcx, rax; unsigned __int64
0x1802332d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802332d6  mov     [rsp+1C0h+var_160], rax
0x1802332db  mov     rsi, rax
0x1802332de  test    r12, r12
0x1802332e1  jz      loc_1802338BE
0x1802332e7  test    rax, rax
0x1802332ea  jz      loc_1802338BE
0x1802332f0  mov     r8d, [rbp+0C0h+var_B0]
0x1802332f4  mov     rcx, r12; void *
0x1802332f7  mov     rdx, [rbp+0C0h+Src]; Src
0x1802332fb  add     r8, r8; Size
0x1802332fe  call    memcpy_0
0x180233303  mov     edx, [rbp+0C0h+var_B0]
0x180233306  xor     ecx, ecx
0x180233308  mov     [r12+rdx*2], cx
0x18023330d  mov     rcx, rsi; void *
0x180233310  mov     r8d, [rbp+0C0h+var_80]
0x180233314  mov     rdx, [rbp+0C0h+var_88]; Src
0x180233318  add     r8, r8; Size
0x18023331b  call    memcpy_0
0x180233320  mov     eax, [rbp+0C0h+var_80]
0x180233323  mov     r8d, [rbp+0C0h+var_70]
0x180233327  mov     rdx, [rbp+0C0h+var_78]; Src
0x18023332b  add     r8, r8; Size
0x18023332e  lea     rcx, [rsi+rax*2]; void *
0x180233332  call    memcpy_0
0x180233337  mov     ecx, [rbp+0C0h+var_80]
0x18023333a  xor     eax, eax
0x18023333c  add     ecx, [rbp+0C0h+var_70]
0x18023333f  xor     r9d, r9d
0x180233342  mov     rdx, r12
0x180233345  mov     [rsi+rcx*2], ax
0x180233349  movzx   r8d, [rbp+0C0h+var_AC]
0x18023334e  mov     rcx, [rbp+0C0h+var_100]
0x180233352  mov     rax, cs:?WinHttpConnect@WINHTTP@@3P6APEAXPEAXPEBGGK@ZEA; void * (*WINHTTP::WinHttpConnect)(void *,ushort const *,ushort,ulong)
0x180233359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023335e  mov     [rbp+0C0h+var_120], rax
0x180233362  test    rax, rax
0x180233365  jnz     short loc_18023337F
0x180233367  call    cs:__imp_GetLastError
0x18023336e  nop     dword ptr [rax+rax+00h]
0x180233373  mov     esi, eax
0x180233375  mov     r12, [rsp+1C0h+var_160]
0x18023337a  jmp     loc_1802338C4
0x18023337f  xor     ecx, ecx
0x180233381  mov     edx, 800000h
0x180233386  cmp     [rbp+0C0h+var_BC], 2
0x18023338a  mov     r8, rsi
0x18023338d  cmovz   ecx, edx
0x180233390  xor     r9d, r9d
0x180233393  mov     dword ptr [rsp+1C0h+hTemplateFile], ecx
0x180233397  xor     edx, edx
0x180233399  lea     rcx, [rbp+0C0h+var_60]
0x18023339d  mov     qword ptr [rsp+1C0h+dwFlagsAndAttributes], rcx
0x1802333a2  mov     rcx, rax
0x1802333a5  mov     rax, cs:?WinHttpOpenRequest@WINHTTP@@3P6APEAXPEAXPEBG111PEAPEBGK@ZEA; void * (*WINHTTP::WinHttpOpenRequest)(void *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const * *,ulong)
0x1802333ac  mov     qword ptr [rsp+1C0h+dwCreationDisposition], r13
0x1802333b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802333b6  mov     [rbp+0C0h+var_130], rax
0x1802333ba  mov     rsi, rax
0x1802333bd  test    rax, rax
0x1802333c0  jz      short loc_180233367
0x1802333c2  mov     r12, [rbp+0C0h+var_128]
0x1802333c6  lea     r9, [rsp+1C0h+var_148]; unsigned int *
0x1802333cb  mov     rcx, [rbp+0C0h+var_100]; void *
0x1802333cf  mov     r8, r12; unsigned __int16 *
0x1802333d2  mov     rdx, rax; void *
0x1802333d5  call    ?MsiWinHttpSendRequestAndReceiveResponse@@YAHPEAX0PEBGPEAK@Z; MsiWinHttpSendRequestAndReceiveResponse(void *,void *,ushort const *,ulong *)
0x1802333da  test    eax, eax
0x1802333dc  jz      short loc_180233367
0x1802333de  cmp     [rsp+1C0h+var_148], 0C8h
0x1802333e6  jz      short loc_1802333EF
0x1802333e8  mov     esi, 2
0x1802333ed  jmp     short loc_180233375
0x1802333ef  lea     rax, [rbp+0C0h+var_138]
0x1802333f3  mov     qword ptr [rsp+1C0h+dwFlagsAndAttributes], r13
0x1802333f8  mov     qword ptr [rsp+1C0h+dwCreationDisposition], rax
0x1802333fd  lea     r9, [rsp+1C0h+lDistanceToMove]
0x180233402  mov     rax, cs:?WinHttpQueryHeaders@WINHTTP@@3P6AHPEAXKPEBG0PEAK2@ZEA; int (*WINHTTP::WinHttpQueryHeaders)(void *,ulong,ushort const *,void *,ulong *,ulong *)
0x180233409  xor     r8d, r8d
0x18023340c  mov     edx, 20000005h
0x180233411  mov     [rbp+0C0h+var_138], 4
0x180233418  mov     rcx, rsi
0x18023341b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180233420  test    eax, eax
0x180233422  jz      loc_180233367
0x180233428  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18023342f  jz      loc_1802334D1
0x180233435  call    ?IsAdmin@@YA_NXZ; IsAdmin(void)
0x18023343a  test    al, al
0x18023343c  jnz     loc_1802334D1
0x180233442  call    ?GetTempDirectory@@YAAEBVIMsiString@@XZ; GetTempDirectory(void)
0x180233447  mov     rdi, rax
0x18023344a  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180233451  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180233458  mov     rax, [rax+10h]
0x18023345c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180233461  mov     rax, [rdi]
0x180233464  mov     rcx, rdi
0x180233467  mov     rsi, [rbp+0C0h+lpTempFileName]
0x18023346b  mov     rax, [rax+50h]
0x18023346f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180233474  mov     r9, rsi; lpTempFileName
0x180233477  lea     rdx, PrefixString; "MSI"
0x18023347e  xor     r8d, r8d; uUnique
0x180233481  mov     rcx, rax; lpPathName
0x180233484  call    cs:__imp_GetTempFileNameW
0x18023348b  nop     dword ptr [rax+rax+00h]
0x180233490  test    eax, eax
0x180233492  jz      loc_180233367
0x180233498  mov     rcx, [rbp+0C0h+lpTempFileName]; lpFileName
0x18023349c  xor     r9d, r9d; lpSecurityAttributes
0x18023349f  mov     [rsp+1C0h+hTemplateFile], r13; hTemplateFile
0x1802334a4  mov     edx, 40000000h; dwDesiredAccess
0x1802334a9  mov     [rsp+1C0h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x1802334b1  mov     [rsp+1C0h+dwCreationDisposition], 5; dwCreationDisposition
0x1802334b9  lea     r8d, [r9+1]; dwShareMode
0x1802334bd  call    cs:__imp_CreateFileW
0x1802334c4  nop     dword ptr [rax+rax+00h]
0x1802334c9  mov     r15, rax
0x1802334cc  jmp     loc_180233614
0x1802334d1  mov     dl, 1; bool
0x1802334d3  lea     rcx, [rsp+1C0h+var_148]; this
0x1802334d8  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x1802334dd  call    ?GetMsiDirectory@@YAAEBVIMsiString@@XZ; GetMsiDirectory(void)
0x1802334e2  mov     rbx, rax
0x1802334e5  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1802334ec  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1802334f3  mov     rax, [rax+10h]
0x1802334f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802334fc  mov     rax, [rbx]
0x1802334ff  mov     rcx, rbx
0x180233502  mov     rsi, [rbp+0C0h+lpTempFileName]
0x180233506  mov     rax, [rax+50h]
0x18023350a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023350f  mov     r9, rsi; lpTempFileName
0x180233512  lea     rdx, PrefixString; "MSI"
0x180233519  xor     r8d, r8d; uUnique
0x18023351c  mov     rcx, rax; lpPathName
0x18023351f  call    cs:__imp_GetTempFileNameW
0x180233526  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
