# DecompressDeltaFileIfNecessary

- ea: `0x18009f8e0`
- end: `0x1800a02e4`
- name: `DecompressDeltaFileIfNecessary`
- size: `2564`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180126dd8`

## callees

- `0x180010cc0`
- `0x180012fe4`
- `0x180013250`
- `0x180016d40`
- `0x1800261e0`
- `0x18002c43c`
- `0x180093c4c`
- `0x180095924`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x18009f8e0`
- `0x1800a02ec`
- `0x1800a0324`
- `0x1800b2fbc`
- `0x1800c516c`
- `0x1800eb920`
- `0x180126dd8`
- `0x180128288`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f9d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009fac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009fe29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ff67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f9d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009fac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009fe29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ff67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0127`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18009fffc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18009fffc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009fab0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009fab0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009f9a3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009fdfb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a00f9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009f9a3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009fdfb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a00f9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a00aa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a00aa`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18009fa7f`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18009fa7f`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18009fef0`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18009fef0`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18009ff53`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18009ff53`

## string_xrefs

- `0x18009f9ef`: `Failed to open payload file:{}`
- `0x1800a0038`: `Failed to copy file from:{} to {}`
- `0x18009fe4d`: `Failed to open baseline file: {}`
- `0x18009fae2`: `Failed to read header structure from file: {}.`
- `0x1800a014f`: `Failed to open payload file: {}`
- `0x18009fc89`: `Failed to get Component Identity as string.`
- `0x1800a0269`: `Payload size invalid or too small, was not delta-compressed for file: {}`
- `0x1800a00c4`: `Unable to delete temp file: {}`
- `0x1800a01e8`: `Failed to decompress delta file: {}, baseline: {}`
- `0x18009ff20`: `.tempcopy`

## pseudocode

```c
__int64 __fastcall DecompressDeltaFileIfNecessary(
        struct CCbsSession *a1,
        __int64 a2,
        __int64 a3,
        wchar_t *a4,
        __int64 a5,
        wchar_t *a6)
{
  __int64 v7; // r8
  wchar_t *v10; // rdi
  int v11; // eax
  unsigned int v12; // ebx
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  unsigned int v15; // r14d
  HANDLE FileW; // rax
  HANDLE v17; // rbx
  signed int LastError; // ebx
  unsigned int v19; // eax
  __int64 v20; // rdx
  unsigned __int64 v21; // r9
  int v22; // edx
  unsigned int v23; // eax
  __int64 v24; // r15
  __int64 v25; // rbx
  __int64 InitPointer; // rax
  int DefinitionIdentityWithVersion; // eax
  int v28; // edx
  int KeyFormFromDefinitionIdentity; // eax
  int v30; // edx
  wchar_t *v31; // rbx
  int v32; // eax
  unsigned int v33; // edi
  int v34; // edx
  int v35; // eax
  HANDLE v36; // rax
  int v37; // edx
  unsigned int v38; // eax
  BOOL FileInformationByHandle; // eax
  DWORD nNumberOfLinks; // ecx
  int v41; // eax
  wchar_t *v42; // rbx
  int v43; // edx
  signed int v44; // edi
  int v45; // r8d
  int v46; // r9d
  int v47; // edx
  unsigned int v48; // eax
  signed int v49; // edi
  int v50; // edx
  unsigned int v51; // eax
  HANDLE v52; // rax
  int v53; // edx
  unsigned int v54; // eax
  int v55; // eax
  int v56; // edx
  int dwCreationDisposition; // [rsp+20h] [rbp-C9h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-C9h]
  wchar_t *v60; // [rsp+40h] [rbp-A9h] BYREF
  int v61[2]; // [rsp+48h] [rbp-A1h] BYREF
  __int64 v62; // [rsp+50h] [rbp-99h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp-91h] BYREF
  struct IDefinitionIdentity *v64; // [rsp+60h] [rbp-89h] BYREF
  LPCWSTR lpNewFileName; // [rsp+68h] [rbp-81h] BYREF
  LPCWSTR v66; // [rsp+70h] [rbp-79h] BYREF
  wchar_t *v67; // [rsp+78h] [rbp-71h] BYREF
  LPCWSTR v68; // [rsp+80h] [rbp-69h] BYREF
  wchar_t *v69; // [rsp+88h] [rbp-61h] BYREF
  unsigned int v70; // [rsp+90h] [rbp-59h] BYREF
  LPCWSTR lpFileName; // [rsp+98h] [rbp-51h] BYREF
  _QWORD Buffer[2]; // [rsp+A0h] [rbp-49h] BYREF
  DWORD NumberOfBytesRead; // [rsp+B0h] [rbp-39h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+B8h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+4Fh]

  v60 = a6;
  v7 = *((_QWORD *)a1 + 138);
  v69 = a4;
  memset(Buffer, 0, 12);
  hFile = 0;
  v10 = 0;
  v62 = 0;
  lpFileName = 0;
  v64 = 0;
  v67 = 0;
  v66 = 0;
  lpNewFileName = 0;
  v11 = SczAllocFormatted(&lpFileName, L"%ws%ws", v7, a5);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = (unsigned int)v11;
    v14 = 3157;
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
      (const char *)v13,
      dwCreationDisposition);
    goto LABEL_100;
  }
  v15 = 3;
  FileW = CreateFileW(lpFileName, 0x80000000, 5u, 0, 3u, 0x80u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hFile,
    FileW);
  v17 = hFile;
  if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      *(_QWORD *)v61 = lpFileName;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to open payload file:{}",
        (__int64)v61);
      if ( LastError > 0 )
        v19 = (unsigned __int16)LastError | 0x80070000;
      else
        v19 = LastError;
      v70 = v19;
      v60 = (wchar_t *)&v70;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        1,
        3,
        (unsigned int)": {0}",
        (__int64)&v60);
    }
    if ( LastError )
    {
      v20 = 3171;
LABEL_11:
      v21 = (unsigned int)LastError;
LABEL_12:
      v12 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v20,
              (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
              (const char *)v21,
              dwCreationDisposition);
      goto LABEL_100;
    }
    goto LABEL_99;
  }
  if ( GetFileSize(hFile, 0) - 12 > 0xFFFFFFF2 )
  {
    v68 = lpFileName;
    if ( LogAdapter::g_Logger )
    {
      LOBYTE(v22) = 1;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        v22,
        1,
        (unsigned int)"Payload size invalid or too small, was not delta-compressed for file: {}",
        (__int64)&v68);
    }
    goto LABEL_99;
  }
  NumberOfBytesRead = 0;
  if ( !ReadFile(v17, Buffer, 0xCu, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      v60 = (wchar_t *)lpFileName;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to read header structure from file: {}.",
        (__int64)&v60);
      if ( LastError > 0 )
        v23 = (unsigned __int16)LastError | 0x80070000;
      else
        v23 = LastError;
      v70 = v23;
      *(_QWORD *)v61 = &v70;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        1,
        3,
        (unsigned int)": {0}",
        (__int64)v61);
    }
    if ( LastError )
    {
      v20 = 3183;
      goto LABEL_11;
    }
LABEL_99:
    v12 = 0;
    goto LABEL_100;
  }
  if ( LOWORD(Buffer[0]) != 17220 || BYTE3(Buffer[0]) != 1 )
    goto LABEL_99;
  if ( BYTE2(Buffer[0]) == 68 )
  {
    v15 = 1;
  }
  else if ( BYTE2(Buffer[0]) != 72 )
  {
    switch ( BYTE2(Buffer[0]) )
    {
      case 'M':
        goto LABEL_99;
      case 'N':
        v15 = 2;
        break;
      case 'S':
        v15 = 5;
        break;
      default:
        goto LABEL_99;
    }
    v24 = v62;
    goto LABEL_62;
  }
  if ( !a2 || !a3 )
  {
    v24 = v62;
LABEL_61:
    if ( ((v15 - 1) & 0xFFFFFFFD) != 0 )
      goto LABEL_99;
LABEL_62:
    memset(&FileInformation, 0, sizeof(FileInformation));
    FileInformationByHandle = GetFileInformationByHandle(v17, &FileInformation);
    nNumberOfLinks = FileInformation.nNumberOfLinks;
    if ( !FileInformationByHandle )
      nNumberOfLinks = 1;
    FileInformation.nNumberOfLinks = nNumberOfLinks;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      0);
    if ( FileInformation.nNumberOfLinks > 1 )
    {
      v41 = SczAllocConcat2Sz(&lpNewFileName, lpFileName, L".tempcopy");
      v12 = v41;
      if ( v41 < 0 )
      {
        v13 = (unsigned int)v41;
        v14 = 3263;
        goto LABEL_40;
      }
      v42 = (wchar_t *)lpNewFileName;
      if ( !MoveFileExW(lpFileName, lpNewFileName, 1u) )
      {
        v44 = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          v60 = v42;
          LogAdapter::Logger::LogNumObjects<AutoScz,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            v43,
            v45,
            v46,
            (__int64)&lpFileName,
            (__int64)&v60);
          if ( v44 > 0 )
            v48 = (unsigned __int16)v44 | 0x80070000;
          else
            v48 = v44;
          v70 = v48;
          LOBYTE(v47) = 1;
          *(_QWORD *)v61 = &v70;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v47,
            3,
            (unsigned int)": {0}",
            (__int64)v61);
        }
        if ( v44 )
        {
          v21 = (unsigned int)v44;
          v20 = 3267;
          goto LABEL_12;
        }
        goto LABEL_99;
      }
      if ( !CopyFileW(v42, lpFileName, 0) )
      {
        v49 = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          v60 = v42;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to copy file from:{} to {}",
            (__int64)&v60,
            (__int64)&lpFileName);
          if ( v49 > 0 )
            v51 = (unsigned __int16)v49 | 0x80070000;
          else
            v51 = v49;
          v70 = v51;
          LOBYTE(v50) = 1;
          *(_QWORD *)v61 = &v70;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v50,
            3,
            (unsigned int)": {0}",
            (__int64)v61);
        }
        if ( v49 )
        {
          v21 = (unsigned int)v49;
          v20 = 3273;
          goto LABEL_12;
        }
        goto LABEL_99;
      }
      if ( !DeleteFileW(v42) )
      {
        v60 = v42;
        LogAdapter::TraceAtLevelLastError<wchar_t const *>(2, "Unable to delete temp file: {}", &v60);
      }
    }
    v52 = CreateFileW(lpFileName, 0xC0000000, 5u, 0, 3u, 0x80u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      v52);
    if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        v60 = (wchar_t *)lpFileName;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to open payload file: {}",
          (__int64)&v60);
        if ( LastError > 0 )
          v54 = (unsigned __int16)LastError | 0x80070000;
        else
          v54 = LastError;
        v70 = v54;
        LOBYTE(v53) = 1;
        *(_QWORD *)v61 = &v70;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v53,
          3,
          (unsigned int)": {0}",
          (__int64)v61);
      }
      if ( LastError )
      {
        v20 = 3296;
        goto LABEL_11;
      }
      goto LABEL_99;
    }
    v55 = DecompressDeltaAndReplaceFile(v15, hFile, v24);
    v12 = v55;
    if ( v55 >= 0 )
      goto LABEL_99;
    v70 = v55;
    if ( LogAdapter::g_Logger )
    {
      *(_QWORD *)v61 = lpFileName;
      v60 = v10;
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to decompress delta file: {}, baseline: {}",
        (__int64)v61,
        (__int64)&v60);
      v68 = (LPCWSTR)&v70;
      LOBYTE(v56) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v56,
        3,
        (unsigned int)": {}",
        (__int64)&v68);
    }
    v14 = 3299;
LABEL_39:
    v13 = v12;
    goto LABEL_40;
  }
  v25 = *(_QWORD *)((char *)Buffer + 4);
  InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v64);
  DefinitionIdentityWithVersion = GetDefinitionIdentityWithVersion(a2, v25, InitPointer);
  v12 = DefinitionIdentityWithVersion;
  if ( DefinitionIdentityWithVersion < 0 )
  {
    v70 = DefinitionIdentityWithVersion;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to generate baseline version");
      v60 = (wchar_t *)&v70;
      LOBYTE(v28) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v28,
        3,
        (unsigned int)": {}",
        (__int64)&v60);
    }
    v14 = 3201;
    goto LABEL_39;
  }
  KeyFormFromDefinitionIdentity = GetKeyFormFromDefinitionIdentity(v64, &v67);
  v12 = KeyFormFromDefinitionIdentity;
  if ( KeyFormFromDefinitionIdentity < 0 )
  {
    v70 = KeyFormFromDefinitionIdentity;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get Component Identity as string.");
      v60 = (wchar_t *)&v70;
      LOBYTE(v30) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v30,
        3,
        (unsigned int)": {}",
        (__int64)&v60);
    }
    v14 = 3204;
    goto LABEL_39;
  }
  v31 = v67;
  v32 = CollectSinglePayloadFileFromAlternativeStore(a1, 1, v64, v67, 0, v69, v60, 0);
  v33 = v32;
  if ( v32 >= 0 )
  {
    dwCreationDisposition = (int)v69;
    v35 = SczAllocFormatted(&v66, L"%s%s\\%s", *((_QWORD *)a1 + 138), v31);
    v12 = v35;
    if ( v35 < 0 )
    {
      v13 = (unsigned int)v35;
      v14 = 3228;
      goto LABEL_40;
    }
    v10 = (wchar_t *)v66;
    v36 = CreateFileW(v66, 0x80000000, 5u, 0, 3u, 0x80u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v62,
      v36);
    v24 = v62;
    if ( ((v62 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        v60 = v10;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to open baseline file: {}",
          (__int64)&v60);
        if ( LastError > 0 )
          v38 = (unsigned __int16)LastError | 0x80070000;
        else
          v38 = LastError;
        v70 = v38;
        LOBYTE(v37) = 1;
        *(_QWORD *)v61 = &v70;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v37,
          3,
          (unsigned int)": {0}",
          (__int64)v61);
      }
      if ( LastError )
      {
        v20 = 3239;
        goto LABEL_11;
      }
      goto LABEL_99;
    }
    v17 = hFile;
    goto LABEL_61;
  }
  v70 = v32;
  if ( LogAdapter::g_Logger )
  {
    v60 = v31;
    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"Failed to collect baseline file: baseline: {}, file: {}",
      (__int64)&v60,
      (__int64)&v69);
    *(_QWORD *)v61 = &v70;
    LOBYTE(v34) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v34,
      3,
      (unsigned int)": {}",
      (__int64)v61);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC94,
    (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
    (const char *)v33,
    dwCreationDispositiona);
  v12 = v33;
LABEL_100:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v66);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v67);
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v64);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v62);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
  return v12;
}

```

## disassembly

```asm
0x18009f8e0  mov     [rsp-8+arg_10], rbx
0x18009f8e5  push    rbp
0x18009f8e6  push    rsi
0x18009f8e7  push    rdi
0x18009f8e8  push    r12
0x18009f8ea  push    r13
0x18009f8ec  push    r14
0x18009f8ee  push    r15
0x18009f8f0  lea     rbp, [rsp-17h]
0x18009f8f5  sub     rsp, 100h
0x18009f8fc  mov     rax, cs:__security_cookie
0x18009f903  xor     rax, rsp
0x18009f906  mov     [rbp+47h+var_40], rax
0x18009f90a  mov     rax, [rbp+47h+arg_28]
0x18009f90e  xor     esi, esi
0x18009f910  mov     [rsp+130h+var_F0], rax
0x18009f915  mov     r12, r8
0x18009f918  mov     r8, [rcx+450h]
0x18009f91f  xor     eax, eax
0x18009f921  mov     r15, rdx
0x18009f924  mov     [rbp+47h+var_A8], r9
0x18009f928  mov     r9, [rbp+47h+arg_20]
0x18009f92c  lea     rdx, aWsWs_1; "%ws%ws"
0x18009f933  mov     r13, rcx
0x18009f936  mov     [rbp+47h+Buffer], rax
0x18009f93a  lea     rcx, [rbp+47h+lpFileName]
0x18009f93e  mov     [rbp+47h+var_88], eax
0x18009f941  mov     [rsp+130h+hFile], rsi
0x18009f946  mov     edi, esi
0x18009f948  mov     [rsp+130h+var_E0], rsi
0x18009f94d  mov     [rbp+47h+lpFileName], rsi
0x18009f951  mov     [rsp+130h+var_D0], rsi
0x18009f956  mov     [rbp+47h+var_B8], rsi
0x18009f95a  mov     [rbp+47h+var_C0], rsi
0x18009f95e  mov     [rsp+130h+lpNewFileName], rsi
0x18009f963  call    SczAllocFormatted
0x18009f968  mov     ebx, eax
0x18009f96a  test    eax, eax
0x18009f96c  jns     short loc_18009F97B
0x18009f96e  mov     r9d, eax
0x18009f971  mov     edx, 0C55h
0x18009f976  jmp     loc_18009FC4B
0x18009f97b  mov     rcx, [rbp+47h+lpFileName]; lpFileName
0x18009f97f  mov     r14d, 3
0x18009f985  mov     [rsp+130h+hTemplateFile], rsi; hTemplateFile
0x18009f98a  xor     r9d, r9d; lpSecurityAttributes
0x18009f98d  mov     [rsp+130h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18009f995  mov     edx, 80000000h; dwDesiredAccess
0x18009f99a  mov     [rsp+130h+dwCreationDisposition], r14d; dwCreationDisposition
0x18009f99f  lea     r8d, [r14+2]; dwShareMode
0x18009f9a3  call    cs:__imp_CreateFileW
0x18009f9aa  nop     dword ptr [rax+rax+00h]
0x18009f9af  mov     rdx, rax
0x18009f9b2  lea     rcx, [rsp+130h+hFile]
0x18009f9b7  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18009f9bc  mov     rbx, [rsp+130h+hFile]
0x18009f9c1  lea     rax, [rbx+1]
0x18009f9c5  test    rax, 0FFFFFFFFFFFFFFFEh
0x18009f9cb  jnz     loc_18009FA7A
0x18009f9d1  call    cs:__imp_GetLastError
0x18009f9d8  nop     dword ptr [rax+rax+00h]
0x18009f9dd  mov     ebx, eax
0x18009f9df  mov     rax, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009f9e6  test    rax, rax
0x18009f9e9  jz      short loc_18009FA53
0x18009f9eb  mov     rcx, [rbp+47h+lpFileName]
0x18009f9ef  lea     r9, aFailedToOpenPa_4; "Failed to open payload file:{}"
0x18009f9f6  mov     qword ptr [rsp+130h+var_E8], rcx
0x18009f9fb  mov     r8d, r14d
0x18009f9fe  lea     rcx, [rsp+130h+var_E8]
0x18009fa03  xor     edx, edx
0x18009fa05  mov     qword ptr [rsp+130h+dwCreationDisposition], rcx
0x18009fa0a  mov     rcx, rax
0x18009fa0d  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18009fa12  test    ebx, ebx
0x18009fa14  jg      short loc_18009FA1A
0x18009fa16  mov     eax, ebx
0x18009fa18  jmp     short loc_18009FA22
0x18009fa1a  movzx   eax, bx
0x18009fa1d  or      eax, 80070000h
0x18009fa22  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009fa29  lea     r9, a0; ": {0}"
0x18009fa30  mov     [rbp+47h+var_A0], eax
0x18009fa33  mov     r8d, r14d
0x18009fa36  lea     rax, [rbp+47h+var_A0]
0x18009fa3a  mov     edx, 1
0x18009fa3f  mov     [rsp+130h+var_F0], rax
0x18009fa44  lea     rax, [rsp+130h+var_F0]
0x18009fa49  mov     qword ptr [rsp+130h+dwCreationDisposition], rax; unsigned int
0x18009fa4e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009fa53  test    ebx, ebx
0x18009fa55  jz      loc_1800A0275
0x18009fa5b  mov     edx, 0C63h; void *
0x18009fa60  mov     r9d, ebx; char *
0x18009fa63  mov     rcx, [rbp+4Fh]; this
0x18009fa67  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x18009fa6e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009fa73  mov     ebx, eax
0x18009fa75  jmp     loc_1800A0277
0x18009fa7a  xor     edx, edx; lpFileSizeHigh
0x18009fa7c  mov     rcx, rbx; hFile
0x18009fa7f  call    cs:__imp_GetFileSize
0x18009fa86  nop     dword ptr [rax+rax+00h]
0x18009fa8b  add     eax, 0FFFFFFF4h
0x18009fa8e  cmp     eax, 0FFFFFFF2h
0x18009fa91  ja      loc_1800A0241
0x18009fa97  lea     r9, [rbp+47h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18009fa9b  mov     [rbp+47h+NumberOfBytesRead], esi
0x18009fa9e  mov     r8d, 0Ch; nNumberOfBytesToRead
0x18009faa4  mov     qword ptr [rsp+130h+dwCreationDisposition], rsi; lpOverlapped
0x18009faa9  lea     rdx, [rbp+47h+Buffer]; lpBuffer
0x18009faad  mov     rcx, rbx; hFile
0x18009fab0  call    cs:__imp_ReadFile
0x18009fab7  nop     dword ptr [rax+rax+00h]
0x18009fabc  test    eax, eax
0x18009fabe  jnz     loc_18009FB58
0x18009fac4  call    cs:__imp_GetLastError
0x18009facb  nop     dword ptr [rax+rax+00h]
0x18009fad0  mov     ebx, eax
0x18009fad2  mov     rax, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009fad9  test    rax, rax
0x18009fadc  jz      short loc_18009FB46
0x18009fade  mov     rcx, [rbp+47h+lpFileName]
0x18009fae2  lea     r9, aFailedToReadHe; "Failed to read header structure from fi"...
0x18009fae9  mov     [rsp+130h+var_F0], rcx
0x18009faee  mov     r8d, r14d
0x18009faf1  lea     rcx, [rsp+130h+var_F0]
0x18009faf6  xor     edx, edx
0x18009faf8  mov     qword ptr [rsp+130h+dwCreationDisposition], rcx
0x18009fafd  mov     rcx, rax
0x18009fb00  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18009fb05  test    ebx, ebx
0x18009fb07  jg      short loc_18009FB0D
0x18009fb09  mov     eax, ebx
0x18009fb0b  jmp     short loc_18009FB15
0x18009fb0d  movzx   eax, bx
0x18009fb10  or      eax, 80070000h
0x18009fb15  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009fb1c  lea     r9, a0; ": {0}"
0x18009fb23  mov     [rbp+47h+var_A0], eax
0x18009fb26  mov     r8d, r14d
0x18009fb29  lea     rax, [rbp+47h+var_A0]
0x18009fb2d  mov     edx, 1
0x18009fb32  mov     qword ptr [rsp+130h+var_E8], rax
0x18009fb37  lea     rax, [rsp+130h+var_E8]
0x18009fb3c  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x18009fb41  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009fb46  test    ebx, ebx
0x18009fb48  jz      loc_1800A0275
0x18009fb4e  mov     edx, 0C6Fh
0x18009fb53  jmp     loc_18009FA60
0x18009fb58  cmp     byte ptr [rbp+47h+Buffer], 44h ; 'D'
0x18009fb5c  jnz     loc_1800A0275
0x18009fb62  cmp     byte ptr [rbp+47h+Buffer+1], 43h ; 'C'
0x18009fb66  jnz     loc_1800A0275
0x18009fb6c  mov     esi, 1
0x18009fb71  cmp     byte ptr [rbp+47h+Buffer+3], sil
0x18009fb75  jnz     loc_1800A0275
0x18009fb7b  movzx   ecx, byte ptr [rbp+47h+Buffer+2]
0x18009fb7f  sub     ecx, 44h ; 'D'
0x18009fb82  jz      short loc_18009FBBA
0x18009fb84  sub     ecx, 4
0x18009fb87  jz      short loc_18009FBBD
0x18009fb89  sub     ecx, 5
0x18009fb8c  jz      loc_1800A0275
0x18009fb92  sub     ecx, esi
0x18009fb94  jz      short loc_18009FBB2
0x18009fb96  cmp     ecx, 5
0x18009fb99  jnz     loc_1800A0275
0x18009fb9f  mov     r14d, ecx
0x18009fba2  mov     r15, [rsp+130h+var_E0]
0x18009fba7  mov     r12d, 3
0x18009fbad  jmp     loc_18009FED5
0x18009fbb2  mov     r14d, 2
0x18009fbb8  jmp     short loc_18009FBA2
0x18009fbba  mov     r14d, esi
0x18009fbbd  test    r15, r15
0x18009fbc0  jz      loc_18009FEBB
0x18009fbc6  test    r12, r12
0x18009fbc9  jz      loc_18009FEBB
0x18009fbcf  mov     rbx, [rbp+47h+Buffer+4]
0x18009fbd3  lea     rcx, [rsp+130h+var_D0]
0x18009fbd8  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18009fbdd  mov     r8, rax
0x18009fbe0  mov     rdx, rbx
0x18009fbe3  mov     rcx, r15
0x18009fbe6  call    ?GetDefinitionIdentityWithVersion@@YAJPEAUIDefinitionIdentity@@T_CBS_VERSION@@PEAPEAU1@@Z; GetDefinitionIdentityWithVersion(IDefinitionIdentity *,_CBS_VERSION,IDefinitionIdentity * *)
0x18009fbeb  mov     ebx, eax
0x18009fbed  test    eax, eax
0x18009fbef  jns     short loc_18009FC60
0x18009fbf1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009fbf8  mov     [rbp+47h+var_A0], eax
0x18009fbfb  test    rcx, rcx
0x18009fbfe  jz      short loc_18009FC43
0x18009fc00  mov     r12d, 3
0x18009fc06  lea     r9, aFailedToGenera; "Failed to generate baseline version"
0x18009fc0d  mov     r8d, r12d
0x18009fc10  xor     edx, edx
0x18009fc12  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18009fc17  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009fc1e  lea     rax, [rbp+47h+var_A0]
0x18009fc22  mov     [rsp+130h+var_F0], rax
0x18009fc27  lea     r9, asc_1802EE7AC; ": {}"
0x18009fc2e  lea     rax, [rsp+130h+var_F0]
0x18009fc33  mov     r8d, r12d
0x18009fc36  mov     dl, sil
0x18009fc39  mov     qword ptr [rsp+130h+dwCreationDisposition], rax; int
0x18009fc3e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009fc43  mov     edx, 0C81h; void *
0x18009fc48  mov     r9d, ebx; char *
0x18009fc4b  mov     rcx, [rbp+4Fh]; this
0x18009fc4f  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x18009fc56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fc5b  jmp     loc_1800A0277
0x18009fc60  mov     rcx, [rsp+130h+var_D0]; struct IDefinitionIdentity *
0x18009fc65  lea     rdx, [rbp+47h+var_B8]; wchar_t **
0x18009fc69  call    ?GetKeyFormFromDefinitionIdentity@@YAJPEAUIDefinitionIdentity@@PEAPEA_W@Z; GetKeyFormFromDefinitionIdentity(IDefinitionIdentity *,wchar_t * *)
0x18009fc6e  mov     ebx, eax
0x18009fc70  test    eax, eax
0x18009fc72  jns     short loc_18009FCD0
0x18009fc74  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009fc7b  mov     [rbp+47h+var_A0], eax
0x18009fc7e  test    rcx, rcx
0x18009fc81  jz      short loc_18009FCC6
0x18009fc83  mov     r12d, 3
0x18009fc89  lea     r9, aFailedToGetCom_0; "Failed to get Component Identity as str"...
0x18009fc90  mov     r8d, r12d
0x18009fc93  xor     edx, edx
0x18009fc95  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18009fc9a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009fca1  lea     rax, [rbp+47h+var_A0]
0x18009fca5  mov     [rsp+130h+var_F0], rax
0x18009fcaa  lea     r9, asc_1802EE7AC; ": {}"
0x18009fcb1  lea     rax, [rsp+130h+var_F0]
0x18009fcb6  mov     r8d, r12d
0x18009fcb9  mov     dl, sil
0x18009fcbc  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x18009fcc1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009fcc6  mov     edx, 0C84h
0x18009fccb  jmp     loc_18009FC48
0x18009fcd0  mov     rcx, [rsp+130h+var_F0]
0x18009fcd5  mov     edx, esi; int
0x18009fcd7  mov     rax, [rbp+47h+var_A8]
0x18009fcdb  mov     rbx, [rbp+47h+var_B8]
0x18009fcdf  mov     r8, [rsp+130h+var_D0]; struct IDefinitionIdentity *
0x18009fce4  mov     r9, rbx; wchar_t *
0x18009fce7  mov     [rsp+130h+var_F8], edi; int
0x18009fceb  mov     [rsp+130h+hTemplateFile], rcx; wchar_t *
0x18009fcf0  mov     rcx, r13; struct CCbsSession *
0x18009fcf3  mov     qword ptr [rsp+130h+dwFlagsAndAttributes], rax; wchar_t *
0x18009fcf8  mov     qword ptr [rsp+130h+dwCreationDisposition], rdi; struct FileContainer *
0x18009fcfd  call    ?CollectSinglePayloadFileFromAlternativeStore@@YAJPEAVCCbsSession@@HPEAUIDefinitionIdentity@@PEB_WPEBUFileContainer@@22H@Z; CollectSinglePayloadFileFromAlternativeStore(CCbsSession *,int,IDefinitionIdentity *,wchar_t const *,FileContainer const *,wchar_t const *,wchar_t const *,int)
0x18009fd02  mov     edi, eax
0x18009fd04  test    eax, eax
0x18009fd06  jns     loc_18009FD95
0x18009fd0c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009fd13  mov     [rbp+47h+var_A0], eax
0x18009fd16  test    rcx, rcx
0x18009fd19  jz      short loc_18009FD76
0x18009fd1b  lea     rax, [rbp+47h+var_A8]
0x18009fd1f  mov     [rsp+130h+var_F0], rbx
0x18009fd24  mov     qword ptr [rsp+130h+dwFlagsAndAttributes], rax
0x18009fd29  lea     r9, aFailedToCollec_14; "Failed to collect baseline file: baseli"...
0x18009fd30  lea     rax, [rsp+130h+var_F0]
0x18009fd35  mov     r12d, 3
0x18009fd3b  mov     r8d, r12d
0x18009fd3e  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x18009fd43  xor     edx, edx
0x18009fd45  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x18009fd4a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009fd51  lea     rax, [rbp+47h+var_A0]
0x18009fd55  mov     qword ptr [rsp+130h+var_E8], rax
0x18009fd5a  lea     r9, asc_1802EE7AC; ": {}"
0x18009fd61  lea     rax, [rsp+130h+var_E8]
0x18009fd66  mov     r8d, r12d
0x18009fd69  mov     dl, sil
0x18009fd6c  mov     qword ptr [rsp+130h+dwCreationDisposition], rax; int
0x18009fd71  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009fd76  mov     rcx, [rbp+4Fh]; this
0x18009fd7a  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x18009fd81  mov     r9d, edi; char *
0x18009fd84  mov     edx, 0C94h; void *
0x18009fd89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fd8e  mov     ebx, edi
0x18009fd90  jmp     loc_1800A0277
0x18009fd95  mov     rax, [rbp+47h+var_A8]
0x18009fd99  lea     rdx, aSSS_0; "%s%s\\%s"
0x18009fda0  mov     r8, [r13+450h]
0x18009fda7  lea     rcx, [rbp+47h+var_C0]
0x18009fdab  mov     r9, rbx
0x18009fdae  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x18009fdb3  call    SczAllocFormatted
0x18009fdb8  mov     ebx, eax
0x18009fdba  test    eax, eax
0x18009fdbc  jns     short loc_18009FDCB
0x18009fdbe  mov     r9d, eax
0x18009fdc1  mov     edx, 0C9Ch
0x18009fdc6  jmp     loc_18009FC4B
0x18009fdcb  mov     rdi, [rbp+47h+var_C0]
0x18009fdcf  mov     r12d, 3
  ... truncated ...
```
