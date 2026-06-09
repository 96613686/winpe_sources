# _CatDBAddCatalog(void *,ulong,ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180017a04`
- end: `0x1800181eb`
- name: `?_CatDBAddCatalog@@YAKPEAXKPEBG11PEAPEAG@Z`
- size: `2023`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, int, unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000a490`

## callees

- `0x1800015b0`
- `0x180001950`
- `0x180002410`
- `0x1800038f0`
- `0x180003d48`
- `0x180004170`
- `0x180004b98`
- `0x180008800`
- `0x180008888`
- `0x18000a57c`
- `0x18000a59c`
- `0x18000ac08`
- `0x18000acbc`
- `0x18000be40`
- `0x18000c7e8`
- `0x1800130a0`
- `0x180017a04`
- `0x1800181f4`
- `0x18001825c`
- `0x18001b4dc`
- `0x18001c7d4`
- `0x18001cf60`
- `0x18001dcf8`
- `0x18001ef4c`
- `0x18001f748`

## import_xrefs

- `CRYPT32!CryptHashCertificate2` at `0x180017de4`
- `CRYPT32!CryptHashCertificate2` at `0x180017de4`
- `CRYPT32!CertFreeCTLContext` at `0x180017e04`
- `CRYPT32!CertFreeCTLContext` at `0x18001816f`
- `CRYPT32!CertFreeCTLContext` at `0x180017e04`
- `CRYPT32!CertFreeCTLContext` at `0x18001816f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017b3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017b3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800181b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800181b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017b02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017b1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017bae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017ca1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017d2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017e3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017f3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001808f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017b02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017b1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017bae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017ca1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017d2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017e3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017f3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001808f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017e22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018192`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800181a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017e22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018192`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800181a5`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180017c19`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180017c19`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180018145`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180018145`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180017c58`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180017c58`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180017fa4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180017fa4`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180017f76`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180018080`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180017f76`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180018080`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x180017eb0`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x180017f05`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x180017eb0`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x180017f05`
- `RPCRT4!RpcRevertToSelf` at `0x180017c95`
- `RPCRT4!RpcRevertToSelf` at `0x180017f2e`
- `RPCRT4!RpcRevertToSelf` at `0x180017f5e`
- `RPCRT4!RpcRevertToSelf` at `0x180017c95`
- `RPCRT4!RpcRevertToSelf` at `0x180017f2e`
- `RPCRT4!RpcRevertToSelf` at `0x180017f5e`
- `RPCRT4!RpcImpersonateClient` at `0x180017b13`
- `RPCRT4!RpcImpersonateClient` at `0x180017e30`
- `RPCRT4!RpcImpersonateClient` at `0x180017b13`
- `RPCRT4!RpcImpersonateClient` at `0x180017e30`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180017e12`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180018182`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180017e12`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180018182`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017b99`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017b99`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180017c7c`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180017ec1`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180017f16`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180018059`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180017c7c`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180017ec1`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180017f16`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180018059`
- `ESENT!JetBeginTransaction` at `0x180017d11`
- `ESENT!JetBeginTransaction` at `0x180017d11`
- `ESENT!JetRollback` at `0x18001810e`
- `ESENT!JetRollback` at `0x18001810e`
- `ESENT!JetCommitTransaction` at `0x180018037`
- `ESENT!JetCommitTransaction` at `0x180018037`

## string_xrefs

- `0x1800180f3`: `AddCatalog(%s):: ERROR_ACCESS_DENIED`

## pseudocode

```c
__int64 __fastcall _CatDBAddCatalog(
        RPC_BINDING_HANDLE BindingHandle,
        int a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 **a6)
{
  struct _JET_DB_STRUCT *v8; // r14
  unsigned __int16 *v9; // rsi
  int v10; // r12d
  const unsigned __int16 *v11; // rcx
  const WCHAR *v12; // rax
  unsigned int v13; // edx
  unsigned __int16 *v14; // rcx
  const unsigned __int16 *v15; // r15
  unsigned int v16; // r8d
  unsigned int Error; // eax
  int v18; // edi
  int v19; // r15d
  DWORD v20; // eax
  unsigned int v21; // ebx
  RPC_STATUS v22; // eax
  unsigned int v23; // edx
  unsigned __int16 *v24; // rcx
  unsigned int v25; // r8d
  unsigned int v26; // edx
  unsigned __int16 *v27; // rcx
  unsigned int v28; // r8d
  __int64 v29; // rax
  unsigned __int64 v30; // rdi
  unsigned __int16 *v31; // rax
  unsigned int v32; // edx
  unsigned __int16 *v33; // rcx
  unsigned int v34; // r8d
  DWORD FileSize; // r15d
  int v36; // r12d
  unsigned int v37; // edx
  unsigned __int16 *v38; // rcx
  RPC_STATUS v39; // eax
  unsigned int v40; // edx
  unsigned __int16 *v41; // rcx
  unsigned int v42; // edx
  unsigned __int16 *v43; // rcx
  JET_ERR v44; // edi
  DWORD v45; // eax
  unsigned int v46; // edx
  unsigned __int16 *v47; // rcx
  unsigned int v48; // edx
  unsigned __int16 *v49; // rcx
  unsigned int v50; // r8d
  BYTE *v51; // rdi
  unsigned int v52; // edx
  unsigned __int16 *v53; // rcx
  RPC_STATUS v54; // eax
  unsigned __int16 *v55; // r15
  unsigned int v56; // edx
  unsigned __int16 *v57; // rcx
  const WCHAR *v58; // r13
  int v59; // edi
  BOOL HardLinkW; // eax
  unsigned int v61; // edx
  unsigned int v62; // edx
  unsigned int v64; // edx
  unsigned __int16 *v65; // rcx
  unsigned int v66; // r8d
  RPC_STATUS v67; // eax
  unsigned int v68; // edx
  unsigned __int16 *v69; // rcx
  unsigned int v70; // r8d
  WCHAR *v71; // r13
  unsigned int v72; // edx
  unsigned __int16 *v73; // rcx
  unsigned int v74; // r8d
  JET_ERR v75; // edi
  unsigned int v76; // edx
  unsigned __int16 *v77; // rcx
  DWORD v78; // eax
  void **v79; // rdi
  DWORD cbEncoded; // [rsp+20h] [rbp-E0h]
  int pbComputedHash; // [rsp+28h] [rbp-D8h]
  int pbComputedHasha; // [rsp+28h] [rbp-D8h]
  int v84; // [rsp+44h] [rbp-BCh]
  const WCHAR *lpFileName; // [rsp+48h] [rbp-B8h]
  int v86; // [rsp+50h] [rbp-B0h]
  int v87; // [rsp+54h] [rbp-ACh] BYREF
  int v88; // [rsp+58h] [rbp-A8h]
  PCCTL_CONTEXT pCtlContext; // [rsp+60h] [rbp-A0h] BYREF
  BYTE *pbEncoded; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  int v92; // [rsp+78h] [rbp-88h]
  struct _JET_DB_STRUCT *v93; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+88h] [rbp-78h]
  HANDLE hFile; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v96; // [rsp+98h] [rbp-68h]
  void **v97; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v98; // [rsp+A8h] [rbp-58h]
  DWORD pcbComputedHash; // [rsp+B0h] [rbp-50h] BYREF
  __int128 FileInformation; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v101; // [rsp+C8h] [rbp-38h]
  int v102; // [rsp+D8h] [rbp-28h]
  _QWORD v103[3]; // [rsp+E0h] [rbp-20h] BYREF
  int v104; // [rsp+F8h] [rbp-8h]
  int v105; // [rsp+FCh] [rbp-4h]
  __int128 v106; // [rsp+100h] [rbp+0h]
  __int128 v107; // [rsp+110h] [rbp+10h]
  BYTE v108[16]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v109; // [rsp+130h] [rbp+30h]
  WCHAR TempFileName; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v111[526]; // [rsp+142h] [rbp+42h] BYREF

  v92 = a2;
  v96 = a3;
  v97 = (void **)a6;
  v86 = 0;
  v8 = 0;
  v93 = 0;
  v84 = 0;
  v9 = 0;
  pCtlContext = 0;
  v10 = (int)a4;
  hObject = 0;
  pbEncoded = 0;
  v87 = 0;
  TempFileName = 0;
  lpExistingFileName = a4;
  memset_0(v111, 0, 0x206u);
  v11 = g_pwszCatalogFileBaseDirectory;
  v88 = 0;
  *a6 = 0;
  hFile = (HANDLE)-1LL;
  pcbComputedHash = 32;
  v12 = _CATDBConstructWSTRPath(v11, a3);
  lpFileName = v12;
  v15 = v12;
  if ( !v12 )
  {
    v16 = 2648;
LABEL_3:
    ErrLog_LogError(v14, v13, v16, 0, 0, pbComputedHash);
    Error = _CatDBGetNonzeroLastError();
    v18 = 0;
    v19 = 0;
LABEL_81:
    v21 = Error;
    goto LABEL_82;
  }
  v20 = _CatDBCanWriteToPathWithImpersonation(BindingHandle, v12);
  v21 = v20;
  if ( v20 )
  {
    SetLastError(v20);
    v16 = 2656;
    goto LABEL_3;
  }
  v22 = RpcImpersonateClient(BindingHandle);
  if ( v22 )
  {
    SetLastError(v22);
    v25 = 2665;
LABEL_41:
    ErrLog_LogError(v24, v23, v25, 0, 0, pbComputedHash);
    v19 = v86;
    v18 = v86;
    Error = _CatDBGetNonzeroLastError();
    goto LABEL_81;
  }
  EnterCriticalSection(&g_CatDBAddDeleteCS);
  v86 = 1;
  v9 = _CatDBCreateNewCatalogFileName(v15, a5, &v87);
  if ( !v9 )
  {
    v28 = 2683;
LABEL_10:
    ErrLog_LogError(v27, v26, v28, 0, 0, pbComputedHash);
    v18 = 0;
LABEL_62:
    v21 = _CatDBGetNonzeroLastError();
    RpcRevertToSelf();
    v19 = v84;
LABEL_82:
    v71 = (WCHAR *)lpFileName;
    goto LABEL_83;
  }
  v29 = -1;
  do
    ++v29;
  while ( v9[v29] );
  v30 = (unsigned int)(v29 + 1);
  v31 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v30);
  *v97 = v31;
  if ( !v31 )
  {
    SetLastError(8u);
    v28 = 2692;
    goto LABEL_10;
  }
  StringCchCopyW(v31, v30, v9);
  v98 = (unsigned __int16 *)_CatDBExtractCatBaseName(v9);
  v18 = 0;
  if ( !(unsigned int)CatUtil_CreateCTLContextFromFileName(
                        v10,
                        (int)&hObject,
                        (int)&pbEncoded,
                        (int)&pCtlContext,
                        cbEncoded,
                        (__int64)&hFile) )
  {
    v34 = 2704;
LABEL_17:
    ErrLog_LogError(v33, v32, v34, 0, 0, pbComputedHasha);
    goto LABEL_62;
  }
  FileSize = GetFileSize(hFile, 0);
  if ( FileSize == -1 && GetLastError() )
  {
    v34 = 2719;
    goto LABEL_17;
  }
  v36 = v87;
  if ( v87 )
  {
    if ( !GetTempFileNameW(g_pwszCatalogFileBaseDirectory, L"TMP", 0, &TempFileName) )
    {
      v34 = 2735;
      goto LABEL_17;
    }
    v88 = 1;
    if ( !CopyFileW(v9, &TempFileName, 0) )
    {
      ErrLog_LogError(v38, v37, 0xABAu, 0, 0, pbComputedHasha);
LABEL_61:
      v18 = v84;
      goto LABEL_62;
    }
  }
  v39 = RpcRevertToSelf();
  if ( v39 )
  {
    SetLastError(v39);
    ErrLog_LogError(v41, v40, 0xAC2u, 0, 0, pbComputedHasha);
    goto LABEL_61;
  }
  if ( !(unsigned int)_CatDBAcquireOpenDatabaseFromCache(&v93, v96, 0, 2, -1) )
  {
    ErrLog_LogError(v43, v42, 0xACEu, 0, 0, 0);
    Error = _CatDBGetNonzeroLastError();
    v8 = v93;
LABEL_80:
    v19 = v18;
    goto LABEL_81;
  }
  v84 = 1;
  CatDBSetWriteJetDatabaseParams();
  v8 = v93;
  v44 = JetBeginTransaction(*((_QWORD *)v93 + 1));
  if ( (unsigned int)_CatDBJET_errFailure(v44) )
  {
    v45 = _CatDBMapJetError(v44);
    SetLastError(v45);
    ErrLog_LogError(v47, v46, 0xADBu, 0, 0, 0);
    Error = _CatDBGetNonzeroLastError();
    v18 = 0;
    v19 = 1;
    goto LABEL_81;
  }
  v18 = 1;
  if ( !(unsigned int)_CatDBDeleteCatalogEntriesFromDatabase(v8, v9, v36 == 0) )
  {
    v50 = 2789;
LABEL_34:
    ErrLog_LogError(v49, v48, v50, 0, 0, 0);
    Error = _CatDBGetNonzeroLastError();
    goto LABEL_80;
  }
  if ( !(unsigned int)_CatDBAddCatalogEntriesToDatabase(v8, pCtlContext, v9) )
  {
    v50 = 2801;
    goto LABEL_34;
  }
  v51 = pbEncoded;
  if ( !CryptHashCertificate2(L"SHA256", 0, 0, pbEncoded, FileSize, v108, &pcbComputedHash) || pcbComputedHash != 32 )
  {
    v70 = 2816;
    goto LABEL_78;
  }
  CertFreeCTLContext(pCtlContext);
  pCtlContext = 0;
  UnmapViewOfFile(v51);
  pbEncoded = 0;
  CloseHandle(hObject);
  hObject = 0;
  v54 = RpcImpersonateClient(BindingHandle);
  if ( v54 )
  {
    SetLastError(v54);
    v25 = 2839;
    goto LABEL_41;
  }
  v55 = v98;
  if ( !(unsigned int)_CatDBIgnoreChangesForFile(v96, v98) )
  {
    ErrLog_LogError(v57, v56, 0xB21u, 0, 0, pbComputedHash);
LABEL_44:
    v18 = 1;
    goto LABEL_62;
  }
  v58 = lpExistingFileName;
  v59 = v92 & 1;
  if ( (v92 & 1) != 0 )
    HardLinkW = CreateHardLinkW(v9, lpExistingFileName, 0);
  else
    HardLinkW = CopyFileW(lpExistingFileName, v9, 0);
  if ( !HardLinkW )
  {
    if ( !v36 )
    {
      ErrLog_LogError(0, v61, 0xB37u, 0, 0, pbComputedHash);
      goto LABEL_61;
    }
    if ( !(unsigned int)_CatDBMoveInUseFileToTempLocation(v9) )
    {
      ErrLog_LogError(0, v62, 0xB42u, 0, 0, pbComputedHash);
      goto LABEL_44;
    }
    if ( !(v59 ? CreateHardLinkW(v9, v58, 0) : CopyFileW(v58, v9, 0)) )
    {
      v66 = 2903;
LABEL_60:
      ErrLog_LogError(v65, v64, v66, 0, 0, pbComputedHash);
      goto LABEL_61;
    }
  }
  v67 = RpcRevertToSelf();
  if ( v67 )
  {
    SetLastError(v67);
    v66 = 2912;
    goto LABEL_60;
  }
  SetFileAttributesW(v9, 0x2004u);
  v102 = 0;
  FileInformation = 0;
  v101 = 0;
  memset_0(v103, 0, 0x40u);
  if ( !GetFileAttributesExW(v9, GetFileExInfoStandard, &FileInformation) )
  {
    ErrLog_LogError(v69, v68, 0xB70u, 0, 0, pbComputedHash);
LABEL_79:
    Error = _CatDBGetNonzeroLastError();
    v18 = 1;
    goto LABEL_80;
  }
  v103[1] = *(_QWORD *)((char *)&FileInformation + 4);
  v103[2] = *(_QWORD *)((char *)&v101 + 4);
  v104 = HIDWORD(v101);
  v105 = v102;
  v103[0] = 0;
  v106 = *(_OWORD *)v108;
  v107 = v109;
  if ( !_CatDBAddNewRowToCatNameAttrTable(v8, v55, (struct _CATALOG_ATTR_STRUCT *)v103) )
  {
    v70 = 2944;
LABEL_78:
    ErrLog_LogError(v53, v52, v70, 0, 0, pbComputedHash);
    goto LABEL_79;
  }
  v71 = (WCHAR *)lpFileName;
  if ( (unsigned int)_CatDBUpdateCatalogPathChangedTime(v8, lpFileName, 1) )
  {
    v75 = JetCommitTransaction(*((_QWORD *)v8 + 1), 0);
    if ( !(unsigned int)_CatDBJET_errFailure(v75) )
    {
      _CatDBReleaseDatabaseToCache(v8, 0);
      goto LABEL_91;
    }
    if ( v36 )
    {
      if ( CopyFileW(&TempFileName, v9, 0) )
        SetFileAttributesW(v9, 0x2004u);
      else
        ErrLog_LogError(v77, v76, 0xB9Du, 0, 0, pbComputedHash);
    }
    v78 = _CatDBMapJetError(v75);
    SetLastError(v78);
    v74 = 2981;
  }
  else
  {
    v74 = 2953;
  }
  ErrLog_LogError(v73, v72, v74, 0, 0, pbComputedHash);
  v18 = 1;
  v21 = _CatDBGetNonzeroLastError();
  v19 = 1;
LABEL_83:
  if ( v21 == 5 )
    ErrLog_LogPrintfW(0, 1, L"AddCatalog(%s):: ERROR_ACCESS_DENIED", lpExistingFileName);
  if ( v18 )
    JetRollback(*((_QWORD *)v8 + 1), 0);
  if ( v19 )
    _CatDBReleaseDatabaseToCache(v8, 0);
  v79 = v97;
  if ( *v97 )
  {
    MIDL_user_free(*v97);
    *v79 = 0;
  }
LABEL_91:
  if ( v88 )
    DeleteFileW(&TempFileName);
  if ( v9 )
    _CatDBFree(v9);
  if ( v71 )
    _CatDBFree(v71);
  if ( pCtlContext )
    CertFreeCTLContext(pCtlContext);
  if ( pbEncoded )
    UnmapViewOfFile(pbEncoded);
  if ( hObject )
    CloseHandle(hObject);
  if ( hFile != (HANDLE)-1LL )
    CloseHandle(hFile);
  if ( v86 )
    LeaveCriticalSection(&g_CatDBAddDeleteCS);
  return v21;
}

```

## disassembly

```asm
0x180017a04  mov     [rsp-8+arg_8], rbx
0x180017a09  push    rbp
0x180017a0a  push    rsi
0x180017a0b  push    rdi
0x180017a0c  push    r12
0x180017a0e  push    r13
0x180017a10  push    r14
0x180017a12  push    r15
0x180017a14  lea     rbp, [rsp-260h]
0x180017a1c  sub     rsp, 360h
0x180017a23  mov     rax, cs:__security_cookie
0x180017a2a  xor     rax, rsp
0x180017a2d  mov     [rbp+290h+var_40], rax
0x180017a34  mov     r15, [rbp+290h+arg_28]
0x180017a3b  xor     eax, eax
0x180017a3d  mov     rdi, [rbp+290h+arg_20]
0x180017a44  mov     rbx, r8
0x180017a47  mov     [rsp+390h+var_318], edx
0x180017a4b  mov     r13, rcx
0x180017a4e  xor     edx, edx; Val
0x180017a50  mov     [rbp+290h+var_2F8], rbx
0x180017a54  mov     r8d, 206h; Size
0x180017a5a  mov     [rbp+290h+var_2F0], r15
0x180017a5e  lea     rcx, [rbp+290h+var_24E]; void *
0x180017a62  mov     [rsp+390h+var_340], eax
0x180017a66  mov     r14d, eax
0x180017a69  mov     [rbp+290h+var_310], rax
0x180017a6d  mov     [rsp+390h+var_34C], eax
0x180017a71  mov     esi, eax
0x180017a73  mov     [rsp+390h+pCtlContext], rax
0x180017a78  mov     r12, r9
0x180017a7b  mov     [rsp+390h+hObject], rax
0x180017a80  mov     [rsp+390h+pbEncoded], rax
0x180017a85  mov     [rsp+390h+var_350], eax
0x180017a89  mov     [rsp+390h+var_33C], eax
0x180017a8d  mov     [rbp+290h+TempFileName], ax
0x180017a91  mov     [rbp+290h+lpExistingFileName], r9
0x180017a95  call    memset_0
0x180017a9a  mov     rcx, cs:?g_pwszCatalogFileBaseDirectory@@3PEAGEA; unsigned __int16 *
0x180017aa1  xor     eax, eax
0x180017aa3  mov     rdx, rbx; unsigned __int16 *
0x180017aa6  mov     [rsp+390h+var_338], eax
0x180017aaa  mov     [r15], rax
0x180017aad  mov     [rbp+290h+hFile], 0FFFFFFFFFFFFFFFFh
0x180017ab5  mov     [rbp+290h+var_2E0], 20h ; ' '
0x180017abc  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x180017ac1  mov     [rsp+390h+lpFileName], rax
0x180017ac6  mov     r15, rax
0x180017ac9  test    rax, rax
0x180017acc  jnz     short loc_180017AEF
0x180017ace  mov     r8d, 0A58h; unsigned int
0x180017ad4  xor     r9d, r9d; unsigned int
0x180017ad7  mov     [rsp+390h+cbEncoded], esi; int
0x180017adb  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180017ae0  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x180017ae5  mov     edi, esi
0x180017ae7  mov     r15d, esi
0x180017aea  jmp     loc_1800180E3
0x180017aef  mov     rdx, r15; lpFileName
0x180017af2  mov     rcx, r13; BindingHandle
0x180017af5  call    ?_CatDBCanWriteToPathWithImpersonation@@YAKPEAXPEBG@Z; _CatDBCanWriteToPathWithImpersonation(void *,ushort const *)
0x180017afa  mov     ebx, eax
0x180017afc  test    eax, eax
0x180017afe  jz      short loc_180017B10
0x180017b00  mov     ecx, eax; dwErrCode
0x180017b02  call    cs:__imp_SetLastError
0x180017b08  mov     r8d, 0A60h
0x180017b0e  jmp     short loc_180017AD4
0x180017b10  mov     rcx, r13; BindingHandle
0x180017b13  call    cs:__imp_RpcImpersonateClient
0x180017b19  test    eax, eax
0x180017b1b  jz      short loc_180017B33
0x180017b1d  mov     ecx, eax; dwErrCode
0x180017b1f  call    cs:__imp_SetLastError
0x180017b25  xor     r13d, r13d
0x180017b28  mov     r8d, 0A69h
0x180017b2e  jmp     loc_180017E4B
0x180017b33  lea     rcx, ?g_CatDBAddDeleteCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180017b3a  call    cs:__imp_EnterCriticalSection
0x180017b40  lea     r8, [rsp+390h+var_33C]; int *
0x180017b45  mov     [rsp+390h+var_340], 1
0x180017b4d  mov     rdx, rdi; unsigned __int16 *
0x180017b50  mov     rcx, r15; unsigned __int16 *
0x180017b53  call    ?_CatDBCreateNewCatalogFileName@@YAPEAGPEBG0PEAH@Z; _CatDBCreateNewCatalogFileName(ushort const *,ushort const *,int *)
0x180017b58  xor     r15d, r15d
0x180017b5b  mov     rsi, rax
0x180017b5e  test    rax, rax
0x180017b61  jnz     short loc_180017B7E
0x180017b63  mov     r8d, 0A7Bh; unsigned int
0x180017b69  xor     r9d, r9d; unsigned int
0x180017b6c  mov     [rsp+390h+cbEncoded], r15d; int
0x180017b71  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180017b76  mov     edi, r14d
0x180017b79  jmp     loc_180017F57
0x180017b7e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017b82  inc     rax
0x180017b85  cmp     [rsi+rax*2], r15w
0x180017b8a  jnz     short loc_180017B82
0x180017b8c  inc     eax
0x180017b8e  mov     ecx, 40h ; '@'; uFlags
0x180017b93  mov     edi, eax
0x180017b95  lea     rdx, [rax+rax]; uBytes
0x180017b99  call    cs:__imp_LocalAlloc
0x180017b9f  mov     rcx, [rbp+290h+var_2F0]
0x180017ba3  mov     [rcx], rax
0x180017ba6  test    rax, rax
0x180017ba9  jnz     short loc_180017BBC
0x180017bab  lea     ecx, [rax+8]; dwErrCode
0x180017bae  call    cs:__imp_SetLastError
0x180017bb4  mov     r8d, 0A84h
0x180017bba  jmp     short loc_180017B69
0x180017bbc  mov     r8, rsi; unsigned __int16 *
0x180017bbf  mov     rdx, rdi; unsigned __int64
0x180017bc2  mov     rcx, rax; unsigned __int16 *
0x180017bc5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017bca  mov     rcx, rsi; Str
0x180017bcd  call    ?_CatDBExtractCatBaseName@@YAPEBGPEBG@Z; _CatDBExtractCatBaseName(ushort const *)
0x180017bd2  mov     [rbp+290h+var_2E8], rax
0x180017bd6  lea     r9, [rsp+390h+pCtlContext]; int
0x180017bdb  lea     rax, [rbp+290h+hFile]
0x180017bdf  mov     rcx, r12; int
0x180017be2  lea     r8, [rsp+390h+pbEncoded]; int
0x180017be7  mov     [rsp+390h+pbComputedHash], rax; int
0x180017bec  lea     rdx, [rsp+390h+hObject]; int
0x180017bf1  call    CatUtil_CreateCTLContextFromFileName
0x180017bf6  xor     edi, edi
0x180017bf8  test    eax, eax
0x180017bfa  jnz     short loc_180017C13
0x180017bfc  mov     r8d, 0A90h; unsigned int
0x180017c02  xor     r9d, r9d; unsigned int
0x180017c05  mov     [rsp+390h+cbEncoded], edi; int
0x180017c09  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180017c0e  jmp     loc_180017F57
0x180017c13  mov     rcx, [rbp+290h+hFile]; hFile
0x180017c17  xor     edx, edx; lpFileSizeHigh
0x180017c19  call    cs:__imp_GetFileSize
0x180017c1f  mov     r15d, eax
0x180017c22  cmp     eax, 0FFFFFFFFh
0x180017c25  jnz     short loc_180017C39
0x180017c27  call    cs:__imp_GetLastError
0x180017c2d  test    eax, eax
0x180017c2f  jz      short loc_180017C39
0x180017c31  mov     r8d, 0A9Fh
0x180017c37  jmp     short loc_180017C02
0x180017c39  mov     r12d, [rsp+390h+var_33C]
0x180017c3e  test    r12d, r12d
0x180017c41  jz      short loc_180017C95
0x180017c43  mov     rcx, cs:?g_pwszCatalogFileBaseDirectory@@3PEAGEA; lpPathName
0x180017c4a  lea     r9, [rbp+290h+TempFileName]; lpTempFileName
0x180017c4e  xor     r8d, r8d; uUnique
0x180017c51  lea     rdx, PrefixString; "TMP"
0x180017c58  call    cs:__imp_GetTempFileNameW
0x180017c5e  test    eax, eax
0x180017c60  jnz     short loc_180017C6A
0x180017c62  mov     r8d, 0AAFh
0x180017c68  jmp     short loc_180017C02
0x180017c6a  xor     r8d, r8d; bFailIfExists
0x180017c6d  mov     [rsp+390h+var_338], 1
0x180017c75  lea     rdx, [rbp+290h+TempFileName]; lpNewFileName
0x180017c79  mov     rcx, rsi; lpExistingFileName
0x180017c7c  call    cs:__imp_CopyFileW
0x180017c82  test    eax, eax
0x180017c84  jnz     short loc_180017C95
0x180017c86  mov     [rsp+390h+cbEncoded], edi
0x180017c8a  mov     r8d, 0ABAh
0x180017c90  jmp     loc_180017F4B
0x180017c95  call    cs:__imp_RpcRevertToSelf
0x180017c9b  test    eax, eax
0x180017c9d  jz      short loc_180017CB6
0x180017c9f  mov     ecx, eax; dwErrCode
0x180017ca1  call    cs:__imp_SetLastError
0x180017ca7  mov     r8d, 0AC2h
0x180017cad  mov     [rsp+390h+cbEncoded], edi
0x180017cb1  jmp     loc_180017F4B
0x180017cb6  mov     rdx, [rbp+290h+var_2F8]
0x180017cba  lea     rcx, [rbp+290h+var_310]
0x180017cbe  mov     dword ptr [rsp+390h+pbComputedHash], edi; int
0x180017cc2  mov     r9d, 2
0x180017cc8  xor     r8d, r8d
0x180017ccb  mov     [rsp+390h+cbEncoded], 0FFFFFFFFh
0x180017cd3  call    ?_CatDBAcquireOpenDatabaseFromCache@@YAHPEAPEAU_JET_DB_STRUCT@@PEBGHW4__MIDL_ICatDBSvc_0002@@KH@Z; _CatDBAcquireOpenDatabaseFromCache(_JET_DB_STRUCT * *,ushort const *,int,__MIDL_ICatDBSvc_0002,ulong,int)
0x180017cd8  test    eax, eax
0x180017cda  jnz     short loc_180017CFC
0x180017cdc  xor     r9d, r9d; unsigned int
0x180017cdf  mov     [rsp+390h+cbEncoded], edi; int
0x180017ce3  mov     r8d, 0ACEh; unsigned int
0x180017ce9  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180017cee  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x180017cf3  mov     r14, [rbp+290h+var_310]
0x180017cf7  jmp     loc_1800180E0
0x180017cfc  mov     [rsp+390h+var_34C], 1
0x180017d04  call    _CatDBSetWriteJetDatabaseParams
0x180017d09  mov     r14, [rbp+290h+var_310]
0x180017d0d  mov     rcx, [r14+8]; sesid
0x180017d11  call    cs:__imp_JetBeginTransaction
0x180017d17  mov     ecx, eax; int
0x180017d19  mov     edi, eax
0x180017d1b  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180017d20  xor     ecx, ecx
0x180017d22  test    eax, eax
0x180017d24  jz      short loc_180017D5E
0x180017d26  mov     ecx, edi; int
0x180017d28  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180017d2d  mov     ecx, eax; dwErrCode
0x180017d2f  call    cs:__imp_SetLastError
0x180017d35  xor     r9d, r9d; unsigned int
0x180017d38  mov     [rsp+390h+cbEncoded], 0; int
0x180017d40  mov     r8d, 0ADBh; unsigned int
0x180017d46  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180017d4b  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x180017d50  mov     edi, [rsp+390h+var_350]
0x180017d54  mov     r15d, [rsp+390h+var_34C]
0x180017d59  jmp     loc_1800180E3
0x180017d5e  mov     r8d, ecx
0x180017d61  test    r12d, r12d
0x180017d64  mov     edi, 1
0x180017d69  mov     rdx, rsi; Str
0x180017d6c  setz    r8b; int
0x180017d70  mov     [rsp+390h+var_350], edi
0x180017d74  mov     rcx, r14; struct _JET_DB_STRUCT *
0x180017d77  call    ?_CatDBDeleteCatalogEntriesFromDatabase@@YAHPEAU_JET_DB_STRUCT@@PEBGH@Z; _CatDBDeleteCatalogEntriesFromDatabase(_JET_DB_STRUCT *,ushort const *,int)
0x180017d7c  test    eax, eax
0x180017d7e  jnz     short loc_180017D9D
0x180017d80  mov     r8d, 0AE5h; unsigned int
0x180017d86  xor     r9d, r9d; unsigned int
0x180017d89  mov     [rsp+390h+cbEncoded], r9d; int
0x180017d8e  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180017d93  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x180017d98  jmp     loc_1800180E0
0x180017d9d  mov     rdx, [rsp+390h+pCtlContext]; struct _CTL_CONTEXT *
0x180017da2  mov     r8, rsi; Str
0x180017da5  mov     rcx, r14; struct _JET_DB_STRUCT *
0x180017da8  call    ?_CatDBAddCatalogEntriesToDatabase@@YAHPEAU_JET_DB_STRUCT@@PEBU_CTL_CONTEXT@@PEBG@Z; _CatDBAddCatalogEntriesToDatabase(_JET_DB_STRUCT *,_CTL_CONTEXT const *,ushort const *)
0x180017dad  test    eax, eax
0x180017daf  jnz     short loc_180017DB9
0x180017db1  mov     r8d, 0AF1h
0x180017db7  jmp     short loc_180017D86
0x180017db9  mov     rdi, [rsp+390h+pbEncoded]
0x180017dbe  lea     rax, [rbp+290h+var_2E0]
0x180017dc2  mov     [rsp+390h+pcbComputedHash], rax; pcbComputedHash
0x180017dc7  lea     rcx, pwszCNGHashAlgid; "SHA256"
0x180017dce  lea     rax, [rbp+290h+var_270]
0x180017dd2  mov     r9, rdi; pbEncoded
0x180017dd5  mov     [rsp+390h+pbComputedHash], rax; int
0x180017dda  xor     r8d, r8d; pvReserved
0x180017ddd  xor     edx, edx; dwFlags
0x180017ddf  mov     [rsp+390h+cbEncoded], r15d; cbEncoded
0x180017de4  call    cs:__imp_CryptHashCertificate2
0x180017dea  xor     r15d, r15d
0x180017ded  test    eax, eax
0x180017def  jz      loc_1800180C4
0x180017df5  cmp     [rbp+290h+var_2E0], 20h ; ' '
0x180017df9  jnz     loc_1800180C4
0x180017dff  mov     rcx, [rsp+390h+pCtlContext]; pCtlContext
0x180017e04  call    cs:__imp_CertFreeCTLContext
0x180017e0a  mov     rcx, rdi; lpBaseAddress
0x180017e0d  mov     [rsp+390h+pCtlContext], r15
0x180017e12  call    cs:__imp_UnmapViewOfFile
0x180017e18  mov     rcx, [rsp+390h+hObject]; hObject
0x180017e1d  mov     [rsp+390h+pbEncoded], r15
0x180017e22  call    cs:__imp_CloseHandle
0x180017e28  mov     rcx, r13; BindingHandle
0x180017e2b  mov     [rsp+390h+hObject], r15
0x180017e30  call    cs:__imp_RpcImpersonateClient
0x180017e36  xor     r13d, r13d
0x180017e39  test    eax, eax
0x180017e3b  jz      short loc_180017E6A
0x180017e3d  mov     ecx, eax; dwErrCode
0x180017e3f  call    cs:__imp_SetLastError
0x180017e45  mov     r8d, 0B17h; unsigned int
0x180017e4b  xor     r9d, r9d; unsigned int
0x180017e4e  mov     [rsp+390h+cbEncoded], r13d; int
0x180017e53  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180017e58  mov     r15d, [rsp+390h+var_340]
0x180017e5d  mov     edi, r15d
0x180017e60  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x180017e65  jmp     loc_1800180E3
0x180017e6a  mov     r15, [rbp+290h+var_2E8]
0x180017e6e  mov     rcx, [rbp+290h+var_2F8]; unsigned __int16 *
0x180017e72  mov     rdx, r15; unsigned __int16 *
0x180017e75  call    ?_CatDBIgnoreChangesForFile@@YAHPEBG0@Z; _CatDBIgnoreChangesForFile(ushort const *,ushort const *)
0x180017e7a  test    eax, eax
0x180017e7c  jnz     short loc_180017E9A
0x180017e7e  mov     [rsp+390h+cbEncoded], r13d; int
0x180017e83  mov     r8d, 0B21h; unsigned int
0x180017e89  xor     r9d, r9d; unsigned int
0x180017e8c  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180017e91  mov     edi, [rsp+390h+var_350]
0x180017e95  jmp     loc_180017F57
0x180017e9a  mov     edi, [rsp+390h+var_318]
0x180017e9e  mov     r13, [rbp+290h+lpExistingFileName]
0x180017ea2  and     edi, 1
0x180017ea5  jz      short loc_180017EB8
0x180017ea7  xor     r8d, r8d; lpSecurityAttributes
0x180017eaa  mov     rdx, r13; lpExistingFileName
0x180017ead  mov     rcx, rsi; lpFileName
0x180017eb0  call    cs:__imp_CreateHardLinkW
0x180017eb6  jmp     short loc_180017EC7
0x180017eb8  xor     r8d, r8d; bFailIfExists
0x180017ebb  mov     rdx, rsi; lpNewFileName
  ... truncated ...
```
