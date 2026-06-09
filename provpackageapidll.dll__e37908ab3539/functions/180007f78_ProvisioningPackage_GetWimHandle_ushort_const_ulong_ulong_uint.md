# ProvisioningPackage::GetWimHandle(ushort const *,ulong,ulong,uint)

- ea: `0x180007f78`
- end: `0x1800088d6`
- name: `?GetWimHandle@ProvisioningPackage@@AEAAJPEBGKKI@Z`
- size: `2398`
- prototype: `HRESULT __fastcall(ProvisioningPackage *this, const unsigned __int16 *, unsigned int, unsigned int, ULONG)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800068b8`
- `0x180008b9c`

## callees

- `0x180001510`
- `0x180001e66`
- `0x1800020a8`
- `0x1800020ec`
- `0x180005424`
- `0x180006014`
- `0x180007f78`
- `0x18000e7b0`
- `0x18000e904`
- `0x18000f6b0`
- `0x18000fc8c`
- `0x18001004c`
- `0x180018440`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000835b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000835b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000800e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000800e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ffb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000801f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000812d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008178`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000865e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000876b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ffb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000801f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000812d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008178`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000865e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000876b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800086b6`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000874c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800087f8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000885e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800086b6`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000874c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800087f8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000885e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800086a0`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800086a0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180008495`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180008495`
- `WIMGAPI!WIMCreateFile` at `0x180007fe4`
- `WIMGAPI!WIMCreateFile` at `0x1800085b8`
- `WIMGAPI!WIMCreateFile` at `0x180007fe4`
- `WIMGAPI!WIMCreateFile` at `0x1800085b8`
- `WIMGAPI!WIMSetReferenceFile` at `0x180008654`
- `WIMGAPI!WIMSetReferenceFile` at `0x180008654`
- `WIMGAPI!WIMSetTemporaryPath` at `0x180008109`
- `WIMGAPI!WIMSetTemporaryPath` at `0x180008109`
- `WIMGAPI!WIMGetAttributes` at `0x1800081c1`
- `WIMGAPI!WIMGetAttributes` at `0x1800085f3`
- `WIMGAPI!WIMGetAttributes` at `0x1800081c1`
- `WIMGAPI!WIMGetAttributes` at `0x1800085f3`
- `WIMGAPI!WIMCloseHandle` at `0x180008006`
- `WIMGAPI!WIMCloseHandle` at `0x180008683`
- `WIMGAPI!WIMCloseHandle` at `0x180008734`
- `WIMGAPI!WIMCloseHandle` at `0x180008006`
- `WIMGAPI!WIMCloseHandle` at `0x180008683`
- `WIMGAPI!WIMCloseHandle` at `0x180008734`

## string_xrefs

- `0x1800080ee`: `    Failed to get temporary folder`
- `0x180008062`: `    Failed to create wim file`
- `0x18000816a`: `    Failed to set temporary path`
- `0x1800082a0`: `    Failed to allocate spParentPath.get()`
- `0x1800082f3`: `    Failed to copy parent path string`
- `0x18000889f`: `    Failed to remove file spec`
- `0x180008402`: `    Failed to allocate spSearchPath.get()`
- `0x180008461`: `    Failed to assemble search path string`
- `0x1800087d8`: `    Failed to assemble file path string`

## pseudocode

```c
HRESULT __fastcall ProvisioningPackage::GetWimHandle(
        ProvisioningPackage *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        ULONG a5)
{
  char v5; // r13
  __int64 v8; // rdi
  __int64 v9; // rsi
  DWORD LastError; // ebx
  signed int v11; // eax
  HRESULT result; // eax
  int TemporaryFolder; // ebx
  struct std::nothrow_t *v14; // rdx
  void *v15; // rcx
  signed int v16; // eax
  bool v17; // sf
  signed int v18; // eax
  signed int v19; // eax
  signed int v20; // eax
  bool v21; // sf
  signed int v22; // eax
  __int64 v23; // rax
  unsigned __int64 v24; // r15
  unsigned __int64 v25; // rax
  unsigned __int64 v26; // kr00_8
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rsi
  int v29; // eax
  const struct std::nothrow_t *v30; // rdx
  int v31; // eax
  unsigned __int16 *v32; // rbx
  wchar_t *v33; // r12
  const wchar_t *i; // rcx
  wchar_t *v35; // rax
  __int64 v36; // rax
  size_t v37; // rbx
  unsigned __int64 v38; // rax
  unsigned __int64 v39; // kr10_8
  unsigned __int16 *v40; // rax
  unsigned __int16 *v41; // r12
  const struct std::nothrow_t *v42; // rdx
  HRESULT v43; // eax
  const struct std::nothrow_t *v44; // rdx
  HANDLE FirstFileW; // rbx
  signed int v46; // eax
  signed int v47; // eax
  __int64 v48; // rcx
  __int64 v49; // rax
  unsigned __int64 v50; // r15
  unsigned __int64 v51; // rax
  WCHAR *v52; // rax
  WCHAR *v53; // r13
  HRESULT v54; // eax
  HRESULT v55; // r15d
  const struct std::nothrow_t *v56; // rdx
  __int64 v57; // r15
  signed int v58; // eax
  bool v59; // sf
  signed int v60; // eax
  bool v61; // sf
  const struct std::nothrow_t *v62; // rdx
  const struct std::nothrow_t *v63; // rdx
  signed int v64; // eax
  signed int v65; // eax
  const struct std::nothrow_t *v66; // rdx
  unsigned int v67; // edi
  const struct std::nothrow_t *v68; // rdx
  const struct std::nothrow_t *v69; // rdx
  signed int v70; // eax
  const struct std::nothrow_t *v71; // rdx
  const struct std::nothrow_t *v72; // rdx
  const struct std::nothrow_t *v73; // rdx
  const struct std::nothrow_t *v74; // rdx
  __int64 v75; // [rsp+20h] [rbp-E0h]
  struct std::nothrow_t *v78; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v79; // [rsp+48h] [rbp-B8h] BYREF
  ProvisioningPackage *v80; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v81; // [rsp+58h] [rbp-A8h]
  HANDLE v82; // [rsp+60h] [rbp-A0h]
  WCHAR *v83; // [rsp+68h] [rbp-98h]
  __int64 v84; // [rsp+70h] [rbp-90h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v86[520]; // [rsp+2D0h] [rbp+1D0h] BYREF
  char Buf1[24]; // [rsp+4D8h] [rbp+3D8h] BYREF
  __int16 v88; // [rsp+4F0h] [rbp+3F0h]
  unsigned __int16 v89; // [rsp+4F2h] [rbp+3F2h]
  _BYTE v90[520]; // [rsp+500h] [rbp+400h] BYREF
  char Buf2[24]; // [rsp+708h] [rbp+608h] BYREF
  __int16 v92; // [rsp+720h] [rbp+620h]

  v5 = a4;
  v80 = this;
  v8 = WIMCreateFile(a2, a3, a4, 64);
  v9 = *((_QWORD *)this + 1);
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    WIMCloseHandle(v9);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 1) = v8;
  if ( !v8 )
  {
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetWimHandle",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      207,
      (unsigned int)v11);
    ProvPackageLog(3, L"    Failed to create wim file");
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v78 = 0;
  TemporaryFolder = GetTemporaryFolder((__int64)L"tw", (LPCWSTR *)&v78);
  v14 = v78;
  v78 = 0;
  v15 = (void *)*((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = v14;
  if ( v15 )
    operator delete(v15, v14);
  if ( TemporaryFolder < 0 )
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetWimHandle",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      213,
      (unsigned int)TemporaryFolder);
    ProvPackageLog(3, L"    Failed to get temporary folder");
    return TemporaryFolder;
  }
  if ( !(unsigned int)WIMSetTemporaryPath(*((_QWORD *)this + 1), *((_QWORD *)this + 4)) )
  {
    v16 = GetLastError();
    v17 = v16 < 0;
    if ( v16 > 0 )
      v17 = 1;
    if ( v17 )
    {
      v18 = GetLastError();
      if ( v18 > 0 )
        v18 = (unsigned __int16)v18 | 0x80070000;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "ProvisioningPackage::GetWimHandle",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
        215,
        (unsigned int)v18);
      ProvPackageLog(3, L"    Failed to set temporary path");
LABEL_19:
      v19 = GetLastError();
      if ( v19 > 0 )
        return (unsigned __int16)v19 | 0x80070000;
      return v19;
    }
  }
  if ( (v5 & 3) == 0 )
    return 0;
  memset_0(v86, 0, 0x230u);
  if ( !(unsigned int)WIMGetAttributes(*((_QWORD *)this + 1), v86, 560) )
  {
    v20 = GetLastError();
    v21 = v20 < 0;
    if ( v20 > 0 )
      v21 = 1;
    if ( v21 )
    {
      v22 = GetLastError();
      if ( v22 > 0 )
        v22 = (unsigned __int16)v22 | 0x80070000;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "ProvisioningPackage::GetWimHandle",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
        233,
        (unsigned int)v22);
      ProvPackageLog(3, L"    Failed to get wim attributes");
      goto LABEL_19;
    }
  }
  if ( v89 <= 1u )
    return 0;
  v23 = -1;
  do
    ++v23;
  while ( a2[v23] );
  v24 = v23 + 1;
  v26 = v23 + 1;
  v25 = 2 * (v23 + 1);
  if ( !is_mul_ok(v26, 2u) )
    v25 = -1;
  v27 = (unsigned __int16 *)operator new[](v25, (const struct std::nothrow_t *)&std::nothrow);
  v28 = v27;
  v81 = v27;
  if ( !v27 )
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetWimHandle",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      240,
      2147942414LL);
    ProvPackageLog(3, L"    Failed to allocate spParentPath.get()");
    return -2147024882;
  }
  v29 = StringCchCopyW(v27, v24, a2);
  TemporaryFolder = v29;
  if ( v29 < 0 )
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetWimHandle",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      242,
      (unsigned int)v29);
    ProvPackageLog(3, L"    Failed to copy parent path string");
LABEL_40:
    operator delete(v28, v30);
    return TemporaryFolder;
  }
  v79 = 0;
  if ( v24 - 1 > 0x7FFF )
  {
    TemporaryFolder = -2147024809;
LABEL_118:
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetWimHandle",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      244,
      (unsigned int)TemporaryFolder);
    ProvPackageLog(3, L"    Failed to remove file spec");
    goto LABEL_40;
  }
  v31 = PathCchSkipRoot(v28, &v79);
  v32 = v79;
  if ( v31 < 0 )
    v32 = v28;
  v33 = &v28[v24];
  if ( v32 >= v33 )
  {
LABEL_51:
    TemporaryFolder = -2147024809;
  }
  else
  {
    for ( i = v32; ; i = v35 + 1 )
    {
      v35 = wcschr(i, 0x5Cu);
      if ( !v35 )
        break;
      v32 = v35;
      if ( v35 >= v33 )
        goto LABEL_51;
    }
    if ( *v32 )
    {
      *v32 = 0;
      PathCchRemoveBackslash(v28, v24);
      TemporaryFolder = 0;
    }
    else
    {
      TemporaryFolder = PathCchRemoveBackslash(v28, v24);
    }
  }
  if ( TemporaryFolder < 0 )
    goto LABEL_118;
  v36 = -1;
  do
    ++v36;
  while ( v28[v36] );
  v37 = v36 + 3;
  v39 = v36 + 3;
  v38 = 2 * (v36 + 3);
  if ( !is_mul_ok(v39, 2u) )
    v38 = -1;
  v40 = (unsigned __int16 *)operator new[](v38, (const struct std::nothrow_t *)&std::nothrow);
  v41 = v40;
  v79 = v40;
  if ( !v40 )
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetWimHandle",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      249,
      2147942414LL);
    ProvPackageLog(3, L"    Failed to allocate spSearchPath.get()");
    goto LABEL_60;
  }
  v43 = PathCchCombineEx(v40, v37, v28, L"*", a5);
  TemporaryFolder = v43;
  if ( v43 < 0 )
  {
    LODWORD(v75) = 251;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetWimHandle",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      v75,
      (unsigned int)v43);
    ProvPackageLog(3, L"    Failed to assemble search path string");
LABEL_63:
    operator delete(v41, v44);
    goto LABEL_40;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(v41, &FindFileData);
  v82 = FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL )
  {
    v46 = GetLastError();
    if ( v46 > 0 )
      v46 = (unsigned __int16)v46 | 0x80070000;
    LODWORD(v75) = 256;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetWimHandle",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      v75,
      (unsigned int)v46);
    ProvPackageLog(3, L"    Failed to find first file");
    v47 = GetLastError();
    TemporaryFolder = v47;
    if ( v47 > 0 )
      TemporaryFolder = (unsigned __int16)v47 | 0x80070000;
    goto LABEL_63;
  }
  while ( (unsigned int)IsDotDirectory(FindFileData.cFileName) || (FindFileData.dwFileAttributes & 0x10) != 0 )
  {
LABEL_94:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      if ( FirstFileW )
        FindClose(FirstFileW);
      operator delete(v41, v62);
      operator delete(v28, v63);
      return 0;
    }
  }
  v48 = -1;
  do
    ++v48;
  while ( FindFileData.cFileName[v48] );
  v49 = -1;
  do
    ++v49;
  while ( v28[v49] );
  v50 = v48 + v49 + 6;
  v51 = 2 * v50;
  if ( !is_mul_ok(v50, 2u) )
    v51 = -1;
  v52 = (WCHAR *)operator new[](v51, (const struct std::nothrow_t *)&std::nothrow);
  v53 = v52;
  v83 = v52;
  if ( v52 )
  {
    v54 = PathCchCombineEx(v52, v50, v28, FindFileData.cFileName, v75);
    v55 = v54;
    if ( v54 < 0 )
    {
      LODWORD(v75) = 274;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "ProvisioningPackage::GetWimHandle",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
        v75,
        (unsigned int)v54);
      ProvPackageLog(3, L"    Failed to assemble file path string");
      operator delete(v53, v71);
      if ( FirstFileW )
        FindClose(FirstFileW);
      operator delete(v41, v72);
      operator delete(v28, v73);
      return v55;
    }
    LODWORD(v75) = a5;
    v57 = WIMCreateFile(v53, a3, a4, 64);
    v84 = v57;
    if ( !v57 )
      goto LABEL_91;
    memset_0(v90, 0, 0x230u);
    if ( (unsigned int)WIMGetAttributes(v57, v90, 560) )
      goto LABEL_90;
    v58 = GetLastError();
    v59 = v58 < 0;
    if ( v58 > 0 )
      v59 = 1;
    if ( v59 )
    {
      v64 = GetLastError();
      if ( v64 > 0 )
        v64 = (unsigned __int16)v64 | 0x80070000;
      LODWORD(v75) = 285;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "ProvisioningPackage::GetWimHandle",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
        v75,
        (unsigned int)v64);
      ProvPackageLog(3, L"    Failed to get wim attributes");
    }
    else
    {
LABEL_90:
      if ( memcmp_0(Buf1, Buf2, 0x10u)
        || v88 == v92
        || (unsigned int)WIMSetReferenceFile(*((_QWORD *)v80 + 1), v53, 0x10000) )
      {
        goto LABEL_91;
      }
      v60 = GetLastError();
      v61 = v60 < 0;
      if ( v60 > 0 )
        v61 = 1;
      if ( !v61 )
      {
LABEL_91:
        if ( (unsigned __int64)(v57 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          WIMCloseHandle(v57);
        operator delete(v53, v56);
        goto LABEL_94;
      }
      v70 = GetLastError();
      if ( v70 > 0 )
        v70 = (unsigned __int16)v70 | 0x80070000;
      LODWORD(v75) = 289;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "ProvisioningPackage::GetWimHandle",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
        v75,
        (unsigned int)v70);
      ProvPackageLog(3, L"    Failed to set wim reference file");
    }
    v65 = GetLastError();
    v67 = v65;
    if ( v65 > 0 )
      v67 = (unsigned __int16)v65 | 0x80070000;
    if ( v57 != -1 )
      WIMCloseHandle(v57);
    operator delete(v53, v66);
    if ( FirstFileW )
      FindClose(FirstFileW);
    operator delete(v41, v68);
    operator delete(v28, v69);
    return v67;
  }
  LODWORD(v75) = 272;
  ProvPackageLog(
    3,
    L"%hs (%hs:%d) - 0x%08x:",
    "ProvisioningPackage::GetWimHandle",
    "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
    v75,
    2147942414LL);
  ProvPackageLog(3, L"    Failed to allocate spFile.get()");
  if ( FirstFileW )
    FindClose(FirstFileW);
  operator delete(v41, v74);
LABEL_60:
  operator delete(v28, v42);
  return -2147024882;
}

```

## disassembly

```asm
0x180007f78  push    rbp
0x180007f7a  push    rbx
0x180007f7b  push    rsi
0x180007f7c  push    rdi
0x180007f7d  push    r12
0x180007f7f  push    r13
0x180007f81  push    r14
0x180007f83  push    r15
0x180007f85  lea     rbp, [rsp-648h]
0x180007f8d  sub     rsp, 748h
0x180007f94  mov     rax, cs:__security_cookie
0x180007f9b  xor     rax, rsp
0x180007f9e  mov     [rbp+680h+var_50], rax
0x180007fa5  mov     r13d, r9d
0x180007fa8  mov     [rsp+780h+var_74C], r9d
0x180007fad  mov     eax, r8d
0x180007fb0  mov     [rsp+780h+var_748], eax
0x180007fb4  mov     r12, rdx
0x180007fb7  mov     r15, rcx
0x180007fba  mov     [rsp+780h+var_730], rcx
0x180007fbf  mov     ecx, [rbp+680h+arg_20]
0x180007fc5  mov     [rsp+780h+var_750], ecx
0x180007fc9  mov     [rsp+780h+var_758], 0
0x180007fd2  mov     dword ptr [rsp+780h+var_760], ecx
0x180007fd6  mov     r9d, 40h ; '@'
0x180007fdc  mov     r8d, r13d
0x180007fdf  mov     edx, eax
0x180007fe1  mov     rcx, r12
0x180007fe4  call    cs:__imp_WIMCreateFile
0x180007fea  mov     rdi, rax
0x180007fed  mov     rsi, [r15+8]
0x180007ff1  lea     rdx, [rsi-1]
0x180007ff5  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180007ff9  ja      short loc_180008014
0x180007ffb  call    cs:__imp_GetLastError
0x180008001  mov     ebx, eax
0x180008003  mov     rcx, rsi
0x180008006  call    cs:__imp_WIMCloseHandle
0x18000800c  mov     ecx, ebx; dwErrCode
0x18000800e  call    cs:__imp_SetLastError
0x180008014  mov     [r15+8], rdi
0x180008018  xor     esi, esi
0x18000801a  test    rdi, rdi
0x18000801d  jnz     short loc_180008089
0x18000801f  call    cs:__imp_GetLastError
0x180008025  mov     r14d, 80070000h
0x18000802b  test    eax, eax
0x18000802d  jle     short loc_180008035
0x18000802f  movzx   eax, ax
0x180008032  or      eax, r14d
0x180008035  mov     dword ptr [rsp+780h+var_758], eax
0x180008039  mov     dword ptr [rsp+780h+var_760], 0CFh
0x180008041  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180008048  lea     r8, aProvisioningpa_3; "ProvisioningPackage::GetWimHandle"
0x18000804f  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180008056  mov     edi, 3
0x18000805b  mov     ecx, edi
0x18000805d  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008062  lea     rdx, aFailedToCreate_1; "    Failed to create wim file"
0x180008069  mov     ecx, edi
0x18000806b  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008070  call    cs:__imp_GetLastError
0x180008076  test    eax, eax
0x180008078  jle     loc_1800088B3
0x18000807e  movzx   eax, ax
0x180008081  or      eax, r14d
0x180008084  jmp     loc_1800088B3
0x180008089  mov     [rsp+780h+var_740], rsi
0x18000808e  lea     rdx, [rsp+780h+var_740]
0x180008093  lea     rcx, aTw; "tw"
0x18000809a  call    ?GetTemporaryFolder@@YAJPEBGPEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z; GetTemporaryFolder(ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> *)
0x18000809f  mov     ebx, eax
0x1800080a1  mov     rdx, [rsp+780h+var_740]; struct std::nothrow_t *
0x1800080a6  mov     [rsp+780h+var_740], rsi
0x1800080ab  mov     rcx, [r15+20h]; void *
0x1800080af  mov     [r15+20h], rdx
0x1800080b3  test    rcx, rcx
0x1800080b6  jz      short loc_1800080BD
0x1800080b8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800080bd  test    ebx, ebx
0x1800080bf  jns     short loc_180008101
0x1800080c1  mov     dword ptr [rsp+780h+var_758], ebx
0x1800080c5  mov     dword ptr [rsp+780h+var_760], 0D5h
0x1800080cd  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800080d4  lea     r8, aProvisioningpa_3; "ProvisioningPackage::GetWimHandle"
0x1800080db  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800080e2  mov     edi, 3
0x1800080e7  mov     ecx, edi
0x1800080e9  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800080ee  lea     rdx, aFailedToGetTem; "    Failed to get temporary folder"
0x1800080f5  mov     ecx, edi
0x1800080f7  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800080fc  jmp     loc_1800088B1
0x180008101  mov     rdx, [r15+20h]
0x180008105  mov     rcx, [r15+8]
0x180008109  call    cs:__imp_WIMSetTemporaryPath
0x18000810f  mov     r14d, 80070000h
0x180008115  test    eax, eax
0x180008117  jnz     short loc_18000818F
0x180008119  call    cs:__imp_GetLastError
0x18000811f  test    eax, eax
0x180008121  jle     short loc_18000812B
0x180008123  movzx   eax, ax
0x180008126  or      eax, r14d
0x180008129  test    eax, eax
0x18000812b  jns     short loc_18000818F
0x18000812d  call    cs:__imp_GetLastError
0x180008133  test    eax, eax
0x180008135  jle     short loc_18000813D
0x180008137  movzx   eax, ax
0x18000813a  or      eax, r14d
0x18000813d  mov     dword ptr [rsp+780h+var_758], eax
0x180008141  mov     dword ptr [rsp+780h+var_760], 0D7h
0x180008149  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180008150  lea     r8, aProvisioningpa_3; "ProvisioningPackage::GetWimHandle"
0x180008157  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000815e  mov     edi, 3
0x180008163  mov     ecx, edi
0x180008165  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000816a  lea     rdx, aFailedToSetTem; "    Failed to set temporary path"
0x180008171  mov     ecx, edi
0x180008173  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008178  call    cs:__imp_GetLastError
0x18000817e  test    eax, eax
0x180008180  jle     short loc_180008188
0x180008182  movzx   eax, ax
0x180008185  or      eax, r14d
0x180008188  mov     ebx, eax
0x18000818a  jmp     loc_1800088B1
0x18000818f  mov     edi, 3
0x180008194  test    dil, r13b
0x180008197  jz      loc_1800088AB
0x18000819d  mov     ebx, 230h
0x1800081a2  mov     r8d, ebx; Size
0x1800081a5  xor     edx, edx; Val
0x1800081a7  lea     rcx, [rbp+680h+var_4B0]; void *
0x1800081ae  call    memset_0
0x1800081b3  mov     r8d, ebx
0x1800081b6  lea     rdx, [rbp+680h+var_4B0]
0x1800081bd  mov     rcx, [r15+8]
0x1800081c1  call    cs:__imp_WIMGetAttributes
0x1800081c7  xor     r13d, r13d
0x1800081ca  test    eax, eax
0x1800081cc  jnz     short loc_180008226
0x1800081ce  call    cs:__imp_GetLastError
0x1800081d4  test    eax, eax
0x1800081d6  jle     short loc_1800081E0
0x1800081d8  movzx   eax, ax
0x1800081db  or      eax, r14d
0x1800081de  test    eax, eax
0x1800081e0  jns     short loc_180008226
0x1800081e2  call    cs:__imp_GetLastError
0x1800081e8  test    eax, eax
0x1800081ea  jle     short loc_1800081F2
0x1800081ec  movzx   eax, ax
0x1800081ef  or      eax, r14d
0x1800081f2  mov     dword ptr [rsp+780h+var_758], eax
0x1800081f6  mov     dword ptr [rsp+780h+var_760], 0E9h
0x1800081fe  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180008205  lea     r8, aProvisioningpa_3; "ProvisioningPackage::GetWimHandle"
0x18000820c  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180008213  mov     ecx, edi
0x180008215  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000821a  lea     rdx, aFailedToGetWim; "    Failed to get wim attributes"
0x180008221  jmp     loc_180008171
0x180008226  cmp     [rbp+680h+var_28E], 1
0x18000822e  jbe     loc_1800088AE
0x180008234  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008238  mov     rax, rcx
0x18000823b  inc     rax
0x18000823e  cmp     [r12+rax*2], r13w
0x180008243  jnz     short loc_18000823B
0x180008245  lea     r15, [rax+1]
0x180008249  mov     eax, 2
0x18000824e  mul     r15
0x180008251  cmovb   rax, rcx
0x180008255  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000825c  mov     rcx, rax; unsigned __int64
0x18000825f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008264  mov     rsi, rax
0x180008267  mov     [rsp+780h+var_728], rax
0x18000826c  test    rax, rax
0x18000826f  jnz     short loc_1800082B7
0x180008271  mov     r14d, 8007000Eh
0x180008277  mov     dword ptr [rsp+780h+var_758], r14d
0x18000827c  mov     dword ptr [rsp+780h+var_760], 0F0h
0x180008284  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000828b  lea     r8, aProvisioningpa_3; "ProvisioningPackage::GetWimHandle"
0x180008292  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180008299  mov     ecx, edi
0x18000829b  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800082a0  lea     rdx, aFailedToAlloca_23; "    Failed to allocate spParentPath.get"...
0x1800082a7  mov     ecx, edi
0x1800082a9  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800082ae  nop
0x1800082af  mov     ebx, r14d
0x1800082b2  jmp     loc_1800088B1
0x1800082b7  mov     r8, r12; unsigned __int16 *
0x1800082ba  mov     rdx, r15; unsigned __int64
0x1800082bd  mov     rcx, rsi; unsigned __int16 *
0x1800082c0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800082c5  mov     ebx, eax
0x1800082c7  test    eax, eax
0x1800082c9  jns     short loc_18000830F
0x1800082cb  mov     dword ptr [rsp+780h+var_758], eax
0x1800082cf  mov     dword ptr [rsp+780h+var_760], 0F2h
0x1800082d7  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800082de  lea     r8, aProvisioningpa_3; "ProvisioningPackage::GetWimHandle"
0x1800082e5  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800082ec  mov     ecx, edi
0x1800082ee  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800082f3  lea     rdx, aFailedToCopyPa_1; "    Failed to copy parent path string"
0x1800082fa  mov     ecx, edi
0x1800082fc  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008301  nop
0x180008302  mov     rcx, rsi; void *
0x180008305  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000830a  jmp     loc_1800088B1
0x18000830f  mov     [rsp+780h+var_738], r13
0x180008314  lea     rax, [r15-1]
0x180008318  cmp     rax, 7FFFh
0x18000831e  ja      loc_180008872
0x180008324  lea     rdx, [rsp+780h+var_738]; unsigned __int16 **
0x180008329  mov     rcx, rsi; unsigned __int16 *
0x18000832c  call    ?PathCchSkipRoot@@YAJPEAGPEAPEAG@Z; PathCchSkipRoot(ushort *,ushort * *)
0x180008331  mov     rbx, [rsp+780h+var_738]
0x180008336  test    eax, eax
0x180008338  cmovs   rbx, rsi
0x18000833c  lea     r12, [rsi+r15*2]
0x180008340  cmp     rbx, r12
0x180008343  jnb     short loc_18000837B
0x180008345  mov     rcx, rbx
0x180008348  jmp     short loc_180008356
0x18000834a  mov     rbx, rax
0x18000834d  cmp     rax, r12
0x180008350  jnb     short loc_18000837B
0x180008352  lea     rcx, [rax+2]; Str
0x180008356  mov     edx, 5Ch ; '\'; Ch
0x18000835b  call    cs:__imp_wcschr
0x180008361  test    rax, rax
0x180008364  jnz     short loc_18000834A
0x180008366  mov     rdx, r15; cchPath
0x180008369  mov     rcx, rsi; pszPath
0x18000836c  cmp     [rbx], r13w
0x180008370  jnz     short loc_180008382
0x180008372  call    PathCchRemoveBackslash
0x180008377  mov     ebx, eax
0x180008379  jmp     short loc_18000838E
0x18000837b  mov     ebx, 80070057h
0x180008380  jmp     short loc_18000838E
0x180008382  mov     [rbx], r13w
0x180008386  call    PathCchRemoveBackslash
0x18000838b  mov     ebx, r13d
0x18000838e  test    ebx, ebx
0x180008390  js      loc_180008877
0x180008396  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000839a  mov     rax, r15
0x18000839d  inc     rax
0x1800083a0  cmp     [rsi+rax*2], r13w
0x1800083a5  jnz     short loc_18000839D
0x1800083a7  lea     rbx, [rax+3]
0x1800083ab  mov     eax, 2
0x1800083b0  mul     rbx
0x1800083b3  cmovb   rax, r15
0x1800083b7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800083be  mov     rcx, rax; unsigned __int64
0x1800083c1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800083c6  mov     r12, rax
0x1800083c9  mov     [rsp+780h+var_738], rax
0x1800083ce  test    rax, rax
0x1800083d1  jnz     short loc_18000841E
0x1800083d3  mov     r14d, 8007000Eh
0x1800083d9  mov     dword ptr [rsp+780h+var_758], r14d
0x1800083de  mov     dword ptr [rsp+780h+var_760], 0F9h
0x1800083e6  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800083ed  lea     r8, aProvisioningpa_3; "ProvisioningPackage::GetWimHandle"
0x1800083f4  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800083fb  mov     ecx, edi
0x1800083fd  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008402  lea     rdx, aFailedToAlloca_15; "    Failed to allocate spSearchPath.get"...
0x180008409  mov     ecx, edi
0x18000840b  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008410  nop
0x180008411  mov     rcx, rsi; void *
0x180008414  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008419  jmp     loc_1800082AF
0x18000841e  lea     r9, pszMore; "*"
0x180008425  mov     r8, rsi; pszPathIn
0x180008428  mov     rdx, rbx; cchPathOut
0x18000842b  mov     rcx, r12; pszPathOut
0x18000842e  call    PathCchCombineEx
0x180008433  mov     ebx, eax
0x180008435  test    eax, eax
0x180008437  jns     short loc_18000847D
0x180008439  mov     dword ptr [rsp+780h+var_758], eax
0x18000843d  mov     dword ptr [rsp+780h+var_760], 0FBh
0x180008445  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000844c  lea     r8, aProvisioningpa_3; "ProvisioningPackage::GetWimHandle"
0x180008453  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000845a  mov     ecx, edi
  ... truncated ...
```
