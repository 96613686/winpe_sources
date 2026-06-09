# CFileAccessor::Init(IURL *,_FILETIME,CREATE_ACCESSOR_FLAGS,CFileHandler *)

- ea: `0x180003970`
- end: `0x180004857`
- name: `?Init@CFileAccessor@@QEAAJPEAUIURL@@U_FILETIME@@W4CREATE_ACCESSOR_FLAGS@@PEAVCFileHandler@@@Z`
- size: `3815`
- prototype: `__int64 __fastcall(__int64, __int64, struct _ACL *, int, __int64)`
- caller_count: `3`
- callee_count: `41`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800034e0`
- `0x180003610`
- `0x180003770`

## callees

- `0x180002a10`
- `0x180002aa0`
- `0x180002c20`
- `0x180002d80`
- `0x180002eb4`
- `0x180003060`
- `0x180003110`
- `0x180003970`
- `0x180004890`
- `0x180004e60`
- `0x180004f60`
- `0x1800055b0`
- `0x180005720`
- `0x180005a50`
- `0x180005c00`
- `0x1800071c0`
- `0x1800076a0`
- `0x180009680`
- `0x180009800`
- `0x18000a800`
- `0x18000b324`
- `0x18000b350`
- `0x18000be50`
- `0x18000be80`
- `0x18000c164`
- `0x18000c680`
- `0x18000e7fc`
- `0x18000e878`
- `0x18000fcd0`
- `0x180010b2c`
- `0x180011135`
- `0x18001e194`
- `0x18001ee48`
- `0x180020be0`
- `0x180020d04`
- `0x180020ecc`
- `0x180021f14`
- `0x180022178`
- `0x180023910`
- `0x180023a4c`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003eff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000444c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003eff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000444c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045cd`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180003c4b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180003f62`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180003c4b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180003f62`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180003aaf`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180003aaf`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180003bfa`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180004107`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180003bfa`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180004107`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000452f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000452f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000474e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000474e`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800045c7`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180004700`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800045c7`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180004700`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800044ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800044ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004442`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000461a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004644`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004769`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004442`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000461a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004644`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004769`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800045fa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800045fa`
- `ntdll!RtlIsPartialPlaceholder` at `0x180003ac2`
- `ntdll!RtlIsPartialPlaceholder` at `0x180003ac2`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180003c19`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180003c19`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180004299`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180004299`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x18000422c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x18000422c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180003bbd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180003bbd`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180003d57`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180004044`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180003d57`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180004044`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18000441b`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18000441b`

## string_xrefs

- `0x1800047bd`: `[SrchCommon] CFileAccessor: Failed 0x%x`
- `0x18000415a`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x180004271`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
__int64 __fastcall CFileAccessor::Init(__int64 a1, __int64 a2, struct _ACL *a3, int a4, __int64 a5)
{
  __int64 v9; // rdx
  int InformationFileWrapper; // r14d
  DWORD FileAttributesW; // eax
  bool v12; // zf
  _DWORD *v13; // rax
  unsigned int v14; // r8d
  unsigned int *Path; // rax
  wchar_t v16; // dx
  wchar_t v17; // r8
  unsigned int v18; // r9d
  int DriveNumberW; // eax
  UINT DriveTypeW; // eax
  int v21; // esi
  ULONG v22; // eax
  ULONG v23; // esi
  unsigned int v24; // edx
  __int64 v25; // rcx
  int v26; // eax
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // r8
  unsigned int v30; // r9d
  unsigned __int64 v31; // rcx
  int v32; // edx
  CFileAccessor *v33; // rcx
  struct _ACL *v34; // rsi
  DWORD LastError; // eax
  int v36; // eax
  CFileAccessor *v37; // rcx
  int v38; // eax
  int v39; // eax
  DWORD v40; // eax
  DWORD v41; // eax
  DWORD v42; // eax
  DWORD v43; // eax
  DWORD v44; // eax
  bool v45; // sf
  _WORD *v46; // rbx
  wchar_t *v47; // rcx
  unsigned __int64 v48; // rax
  __int64 v49; // rsi
  unsigned __int64 v50; // rax
  unsigned int *v51; // rax
  __int64 v52; // rax
  int v53; // edx
  const wchar_t *v54; // rcx
  int v55; // eax
  DWORD SecurityInfo; // ebx
  void *v57; // r8
  DWORD v58; // eax
  int v59; // edx
  int v60; // r9d
  signed int v61; // eax
  void *v62; // rbx
  HLOCAL v63; // rax
  HLOCAL v64; // rcx
  PSECURITY_DESCRIPTOR v65; // rcx
  PSECURITY_DESCRIPTOR *v66; // rsi
  struct _SECURITY_DESCRIPTOR *v67; // rbx
  const wchar_t *Buffer; // rax
  HLOCAL v69; // rcx
  int v71; // edx
  unsigned int ppsidGroup; // [rsp+20h] [rbp-2A8h]
  DWORD dwBufferLength; // [rsp+40h] [rbp-288h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+44h] [rbp-284h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-280h] BYREF
  WINBOOL bDaclPresent[2]; // [rsp+50h] [rbp-278h] BYREF
  _DWORD *v77; // [rsp+58h] [rbp-270h]
  void **p_hMem; // [rsp+60h] [rbp-268h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-260h] BYREF
  char v80; // [rsp+70h] [rbp-258h]
  _DWORD *v81; // [rsp+78h] [rbp-250h]
  PACL ppDacl; // [rsp+80h] [rbp-248h] BYREF
  PACL pDacl[2]; // [rsp+88h] [rbp-240h] BYREF
  int *v84; // [rsp+98h] [rbp-230h]
  __int64 v85; // [rsp+A0h] [rbp-228h]
  _DWORD *v86; // [rsp+A8h] [rbp-220h]
  __int64 v87; // [rsp+B0h] [rbp-218h] BYREF
  _BYTE pAbsoluteSecurityDescriptor[80]; // [rsp+C0h] [rbp-208h] BYREF
  __int128 FileInformation; // [rsp+110h] [rbp-1B8h] BYREF
  __int128 v90; // [rsp+120h] [rbp-1A8h]
  __int64 v91; // [rsp+130h] [rbp-198h]
  void **v92; // [rsp+140h] [rbp-188h] BYREF
  LPWSTR v93; // [rsp+148h] [rbp-180h]
  unsigned int v94; // [rsp+150h] [rbp-178h]
  int v95; // [rsp+154h] [rbp-174h]
  wchar_t v96[68]; // [rsp+158h] [rbp-170h] BYREF
  void **v97; // [rsp+1E0h] [rbp-E8h] BYREF
  LPCWSTR pszPath; // [rsp+1E8h] [rbp-E0h]
  __int64 v99; // [rsp+1F0h] [rbp-D8h]
  wchar_t v100[68]; // [rsp+1F8h] [rbp-D0h] BYREF
  WCHAR RootPathName[4]; // [rsp+280h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+0h]

  v85 = a1;
  ppDacl = a3;
  *(_DWORD *)(a1 + 856) = 1;
  v84 = (int *)(a1 + 936);
  *(_DWORD *)(a1 + 936) = 0;
  v86 = (_DWORD *)(a1 + 144);
  *(_DWORD *)(a1 + 144) = 0;
  *(_DWORD *)(a1 + 148) = 0;
  v81 = (_DWORD *)(a1 + 940);
  *(_DWORD *)(a1 + 940) = 0;
  *(_QWORD *)(a1 + 864) = 0;
  *(_QWORD *)(a1 + 872) = 0;
  *(_QWORD *)(a1 + 880) = 0;
  *(_QWORD *)(a1 + 888) = 0;
  memset_0((void *)(a1 + 944), 0, 0x250u);
  *(_QWORD *)(a1 + 896) = a5;
  v77 = (_DWORD *)(a1 + 860);
  *(_DWORD *)(a1 + 860) = a4;
  *(_WORD *)(a1 + 88) = 0;
  *(_BYTE *)(a1 + 90) = 0;
  *(_DWORD *)(a1 + 92) = 0;
  dwBufferLength = 0;
  pszPath = v100;
  v99 = 65;
  v100[0] = 0;
  v97 = &TLMString<64,64,32767>::`vftable';
  if ( !a2 )
  {
    InformationFileWrapper = -2147467261;
    goto LABEL_3;
  }
  InformationFileWrapper = ImportLMString<IURL,long (IURL::*)(wchar_t * const,unsigned long,unsigned long *)>(
                             a2,
                             v9,
                             a1 + 248);
  if ( InformationFileWrapper )
    CURL::Init((CURL *)(a1 + 224), &qword_18002A7A0, v14);
  else
    InformationFileWrapper = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 48LL))(a2, a1 + 664);
  if ( InformationFileWrapper >= 0 )
  {
    Path = (unsigned int *)CURL::GetPath(a1 + 224, &v87);
    ((void (__fastcall *)(void ***, __int64, _QWORD, _QWORD))v97[4])(
      &v97,
      *(_QWORD *)(*((_QWORD *)Path + 1) + 8LL) + 2LL * *Path,
      0,
      Path[1]);
    CLMString::ReplaceAll((CLMString *)&v97, v16, v17, v18);
    (*(void (__fastcall **)(__int64, LPCWSTR, _QWORD, __int64))(*(_QWORD *)(a1 + 696) + 32LL))(
      a1 + 696,
      pszPath,
      0,
      0xFFFFFFFFLL);
    ConvertLongPathName((CLMString *)(a1 + 696));
    DriveNumberW = PathGetDriveNumberW(pszPath);
    if ( DriveNumberW == -1 )
    {
      dwBufferLength = 0;
      InitOnceExecuteOnce(
        &g_initOnceOnPerUserCatalogCheck,
        _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
        0,
        0);
      if ( !g_isPerUserCatalogEnabled )
      {
LABEL_14:
        InformationFileWrapper = -2147218169;
        goto LABEL_3;
      }
      dwBufferLength = 3;
    }
    else
    {
      wcscpy(&RootPathName[1], L":\\");
      RootPathName[0] = DriveNumberW + 65;
      DriveTypeW = GetDriveTypeW(RootPathName);
      dwBufferLength = DriveTypeW;
      if ( DriveTypeW != 3 && (DriveTypeW != 2 || (unsigned int)SHWindowsPolicy(POLID_DisableRemovableDriveIndexing)) )
        goto LABEL_14;
    }
  }
LABEL_3:
  v87 = a1 + 696;
  FileAttributesW = GetFileAttributesW(*(LPCWSTR *)(a1 + 704));
  if ( FileAttributesW == -1 )
  {
    v13 = v77;
  }
  else
  {
    v12 = (unsigned __int8)RtlIsPartialPlaceholder(FileAttributesW, 0) == 0;
    v13 = v77;
    if ( !v12 )
    {
      *v77 |= 8u;
      *(_BYTE *)(a1 + 89) = 1;
    }
  }
  if ( InformationFileWrapper < 0 )
    goto LABEL_187;
  if ( (*v13 & 4) != 0 )
  {
    InformationFileWrapper = CFileAccessor::OpenHandleForReadingSD((CFileAccessor *)a1, (wchar_t *)pszPath);
  }
  else
  {
    v21 = *v13 & 8;
    v22 = 131200;
    if ( !v21 )
      v22 = 0x80000000;
    SecurityDescriptorSize = v22;
    InformationFileWrapper = CFileAccessor::OpenOplockedHandle((CFileAccessor *)a1, pszPath, v22);
    if ( InformationFileWrapper != -2147216891 || v21 )
    {
      v23 = SecurityDescriptorSize;
    }
    else
    {
      v23 = 131200;
      InformationFileWrapper = CFileAccessor::OpenOplockedHandle((CFileAccessor *)a1, pszPath, 0x20080u);
    }
    *v81 = v23 != 0x80000000;
  }
  if ( InformationFileWrapper < 0 )
    goto LABEL_187;
  if ( (unsigned int)CFileAccessor::IsOplockBroken((CFileAccessor *)a1) )
  {
    InformationFileWrapper = -2147024864;
    goto LABEL_187;
  }
  InformationFileWrapper = CFileAccessor::CheckIfReparseTagAllowed((CFileAccessor *)a1);
  if ( InformationFileWrapper < 0 )
    goto LABEL_187;
  FileInformation = 0;
  v90 = 0;
  v91 = 0;
  if ( GetFileInformationByHandleEx(*(HANDLE *)(a1 + 104), FileBasicInfo, &FileInformation, 0x28u) )
  {
    v24 = FileInformation;
    *(_DWORD *)(a1 + 872) = FileInformation;
    *(_DWORD *)(a1 + 948) = v24;
    v25 = DWORD1(FileInformation);
    *(_DWORD *)(a1 + 876) = DWORD1(FileInformation);
    *(_DWORD *)(a1 + 952) = v25;
    v26 = DWORD2(FileInformation);
    *(_DWORD *)(a1 + 880) = DWORD2(FileInformation);
    *(_DWORD *)(a1 + 956) = v26;
    v27 = HIDWORD(FileInformation);
    *(_DWORD *)(a1 + 884) = HIDWORD(FileInformation);
    *(_DWORD *)(a1 + 960) = v27;
    v28 = v90;
    *(_DWORD *)(a1 + 864) = v90;
    *(_DWORD *)(a1 + 964) = v28;
    v29 = DWORD1(v90);
    *(_DWORD *)(a1 + 868) = DWORD1(v90);
    *(_DWORD *)(a1 + 968) = v29;
    v30 = DWORD2(v90);
    if ( *((_QWORD *)&v90 + 1) )
    {
      *(_DWORD *)(a1 + 888) = DWORD2(v90);
      v25 = HIDWORD(v90);
      v24 = v30;
    }
    else
    {
      if ( v28 )
      {
        *(_DWORD *)(a1 + 888) = v28;
        *(_DWORD *)(a1 + 892) = v29;
        v24 = v28;
        v25 = v29;
        goto LABEL_39;
      }
      *(_DWORD *)(a1 + 888) = v24;
    }
    *(_DWORD *)(a1 + 892) = v25;
LABEL_39:
    if ( (*(_BYTE *)v77 & 4) != 0 )
    {
      v31 = v24 | (unsigned __int64)(v25 << 32);
      if ( v31 )
      {
        InformationFileWrapper = 0;
        *(_QWORD *)(a1 + 888) = v31 - 1;
      }
      else
      {
        InformationFileWrapper = -2147024362;
      }
    }
    v32 = v91;
    hMem = (HLOCAL)((v91 & 7 | ((unsigned int)v91 >> 2) & 8) + *(_QWORD *)(a1 + 888));
    v33 = (CFileAccessor *)(unsigned int)hMem;
    *(_QWORD *)bDaclPresent = hMem;
    *(_QWORD *)(a1 + 888) = hMem;
    v34 = (struct _ACL *)(a1 + 904);
    *(_DWORD *)(a1 + 904) = v32;
    *(_DWORD *)(a1 + 944) = v32;
    *(_DWORD *)(a1 + 980) = *(_DWORD *)(a1 + 92);
    if ( InformationFileWrapper >= 0 )
    {
      if ( (v32 & 0x400) == 0 )
        goto LABEL_47;
      if ( !*(_BYTE *)(a1 + 88) )
      {
LABEL_48:
        InformationFileWrapper = CFileAccessor::CheckIfReparseTagAllowed((CFileAccessor *)a1);
        *(_DWORD *)(a1 + 980) = *(_DWORD *)(a1 + 92);
        goto LABEL_50;
      }
    }
    if ( (v32 & 0x400) != 0 )
      goto LABEL_50;
LABEL_47:
    if ( !*(_BYTE *)(a1 + 88) )
      goto LABEL_50;
    goto LABEL_48;
  }
  LastError = GetLastError();
  InformationFileWrapper = HResultFromFileStatus(LastError, a1 + 696);
  v34 = (struct _ACL *)(a1 + 904);
LABEL_50:
  pDacl[1] = v34;
  if ( InformationFileWrapper < 0 )
    goto LABEL_187;
  v36 = *(_DWORD *)&v34->AclRevision;
  if ( (*(_DWORD *)&v34->AclRevision & 0x10) == 0 )
  {
    if ( (v36 & 0x100) != 0 )
    {
      InformationFileWrapper = -2147218169;
      goto LABEL_187;
    }
LABEL_59:
    if ( InformationFileWrapper == 266755 )
      goto LABEL_68;
    goto LABEL_60;
  }
  if ( (v36 & 0x700) == 0 )
    goto LABEL_59;
  if ( *(_BYTE *)(a1 + 90) != 1 )
  {
    InitOnceExecuteOnce(
      &g_initOnceOnPerUserCatalogCheck,
      _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
      0,
      0);
    if ( !g_isPerUserCatalogEnabled )
    {
      InformationFileWrapper = -2147218169;
      goto LABEL_187;
    }
  }
  InformationFileWrapper = 0;
LABEL_60:
  if ( (unsigned int)a3 > 1 || HIDWORD(ppDacl) )
  {
    *(_DWORD *)(a1 + 856) = 0;
    if ( (v34->AclRevision & 0x10) == 0 )
    {
      if ( CFileAccessor::WasFileModified(v33, (struct _FILETIME)a3, *(struct _FILETIME *)(a1 + 888)) )
      {
        if ( !CFileAccessor::WasFileModified(v37, (struct _FILETIME)a3, *(struct _FILETIME *)(a1 + 864)) )
          *v81 = 1;
        *(_DWORD *)(a1 + 856) = 1;
      }
      else
      {
        InformationFileWrapper = 266755;
      }
    }
  }
LABEL_68:
  if ( (unsigned int)CFileAccessor::IsOplockBroken((CFileAccessor *)a1) )
  {
    InformationFileWrapper = -2147024864;
    goto LABEL_187;
  }
  if ( !*(_DWORD *)(a1 + 856) && (v34->AclRevision & 0x10) == 0 )
    goto LABEL_184;
  FileInformation = 0;
  *(_QWORD *)&v90 = 0;
  if ( GetFileInformationByHandleEx(*(HANDLE *)(a1 + 104), FileStandardInfo, &FileInformation, 0x18u) )
  {
    v38 = DWORD2(FileInformation);
    *(_DWORD *)(a1 + 912) = DWORD2(FileInformation);
    *(_DWORD *)(a1 + 976) = v38;
    v39 = HIDWORD(FileInformation);
    *(_DWORD *)(a1 + 916) = HIDWORD(FileInformation);
    *(_DWORD *)(a1 + 972) = v39;
    goto LABEL_113;
  }
  v40 = GetLastError();
  InformationFileWrapper = v40;
  if ( v40 != 3 )
  {
    if ( v40 > 0x56 )
    {
      v41 = v40 - 148;
      if ( v41 )
      {
        v42 = v41 - 22;
        if ( v42 )
        {
          v43 = v42 - 1081;
          if ( v43 )
          {
            v44 = v43 - 75;
            if ( !v44 )
              goto LABEL_82;
            if ( v44 != 3024 )
            {
LABEL_88:
              v45 = InformationFileWrapper < 0;
              if ( InformationFileWrapper <= 0 )
                goto LABEL_114;
              InformationFileWrapper = (unsigned __int16)InformationFileWrapper | 0x80070000;
              goto LABEL_113;
            }
          }
LABEL_90:
          InformationFileWrapper = -2147216890;
          goto LABEL_113;
        }
      }
LABEL_91:
      InformationFileWrapper = -2147216896;
      goto LABEL_113;
    }
    if ( v40 == 86 )
    {
LABEL_82:
      InformationFileWrapper = -2147216891;
      goto LABEL_113;
    }
    if ( v40 != 2 )
    {
      if ( v40 != 5 )
      {
        if ( v40 != 54 )
        {
          if ( v40 != 58 )
          {
            if ( v40 == 65 )
              goto LABEL_82;
            goto LABEL_88;
          }
          goto LABEL_90;
        }
        goto LABEL_91;
      }
      goto LABEL_82;
    }
  }
  if ( GetDriveTypeW(*(LPCWSTR *)(a1 + 704)) != 4 )
  {
    v46 = *(_WORD **)(a1 + 704);
    v92 = &CLMString::`vftable';
    v47 = v96;
    v93 = v96;
    v94 = 65;
    if ( !v46 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
        (const char *)0x80070057LL,
        ppsidGroup);
    v48 = -1;
    do
      ++v48;
    while ( v46[v48] );
    if ( v48 > 0xFFFFFFFF )
      goto LABEL_119;
    v49 = (unsigned int)v48;
    SecurityDescriptorSize = v48;
    v50 = (unsigned int)v48 + 1LL;
    if ( v50 > 0xFFFFFFFF )
      goto LABEL_119;
    if ( (unsigned int)v50 > 0x41 )
    {
      v51 = (unsigned int *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(
                              &SecurityDescriptorSize,
                              bDaclPresent);
      CLMString::GrowInConstructor((CLMString *)&v92, *v51);
      v47 = v93;
    }
    if ( !is_mul_ok(2u, v49) )
LABEL_119:
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    memcpy_0(v47, v46, (unsigned int)(2 * v49));
    v95 = v49;
    v93[v49] = 0;
    v92 = &TLMString<64,64,32767>::`vftable';
    if ( v94 < 0x104 )
      TLMString<192,64,32767>::GrowString(&v92, 260);
    if ( PathStripToRootW(v93) )
    {
      v52 = -1;
      do
        ++v52;
      while ( v93[v52] );
      if ( (unsigned int)v52 >= v94 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xFE,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
          (const char *)0xCE,
          ppsidGroup);
      v95 = v52;
      v93[(unsigned int)v52] = 0;
      if ( !PathFileExistsW(v93) )
      {
        v92 = &TLMString<64,64,32767>::`vftable';
        CLMString::DeleteBuf((CLMString *)&v92, v96);
        InformationFileWrapper = -2147216890;
        v34 = (struct _ACL *)(a1 + 904);
        goto LABEL_113;
      }
      v92 = &TLMString<64,64,32767>::`vftable';
      CLMString::DeleteBuf((CLMString *)&v92, v96);
    }
    else
    {
      TLMString<64,64,32767>::~TLMString<64,64,32767>(&v92);
    }
    v34 = (struct _ACL *)(a1 + 904);
  }
  InformationFileWrapper = -2147216895;
LABEL_113:
  v45 = InformationFileWrapper < 0;
LABEL_114:
  if ( !v45 )
  {
    if ( (unsigned int)CFileAccessor::IsOplockBroken((CFileAccessor *)a1) )
    {
      InformationFileWrapper = -2147024864;
    }
    else
    {
      InformationFileWrapper = NtQueryInformationFileWrapper(*(void **)(a1 + 104), (union _LARGE_INTEGER *)(a1 + 1536));
      if ( InformationFileWrapper >= 0 && (unsigned int)CFileAccessor::IsOplockBroken((CFileAccessor *)a1) )
        InformationFileWrapper = -2147024864;
    }
  }
  if ( (*(_DWORD *)&v34->AclRevision & 0x10) == 0
    && (*(_DWORD *)&v34->AclRevision & 0x4000) != 0
    && !CFileAccessor::IsFileFANCIOrSuperHidden((CFileAccessor *)a1)
    && (*(_BYTE *)v77 & 0xC) == 0 )
  {
    if ( (unsigned int)GetPolicyDwordAsBool(v54, v53) || (v12 = !IsCDPLEnabled(), v55 = 0, !v12) )
      v55 = 1;
    *v84 = v55;
  }
  if ( InformationFileWrapper >= 0 )
  {
    if ( (unsigned int)CFileAccessor::IsOplockBroken((CFileAccessor *)a1) )
    {
      InformationFileWrapper = -2147024864;
      goto LABEL_187;
    }
    hMem = 0;
    ppDacl = 0;
    p_hMem = &hMem;
    SecurityDescriptor = 0;
    v80 = 1;
    SecurityInfo = GetSecurityInfo(*(HANDLE *)(a1 + 104), SE_FILE_OBJECT, 7u, 0, 0, &ppDacl, 0, &SecurityDescriptor);
    if ( v80 )
    {
      v57 = *p_hMem;
      *p_hMem = SecurityDescriptor;
      if ( v57 )
        LocalFree(v57);
    }
    if ( !SecurityInfo
      || (v58 = GetLastError(),
          InformationFileWrapper = HResultFromFileStatus(v58, a1 + 696),
          InformationFileWrapper >= 0) )
    {
      if ( (unsigned int)CFileAccessor::IsOplockBroken((CFileAccessor *)a1) )
        InformationFileWrapper = -2147024864;
    }
    if ( dwBufferLength != 2 || ppDacl )
    {
LABEL_166:
      if ( InformationFileWrapper < 0 )
        goto LABEL_182;
      if ( (*(_DWORD *)&v34->AclRevision & 0x10) != 0
        || (*(_DWORD *)&v34->AclRevision & 0x4000) == 0
        || CFileAccessor::IsFileFANCIOrSuperHidden((CFileAccessor *)a1)
        || (*(_BYTE *)v77 & 0xC) != 0
        || !*v84
        || *v81 )
      {
        v66 = (PSECURITY_DESCRIPTOR *)(a1 + 928);
        wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::swap(
          a1 + 928,
          &hMem);
      }
      else
      {
        v66 = (PSECURITY_DESCRIPTOR *)(a1 + 928);
        p_hMem = (void **)(a1 + 928);
        SecurityDescriptor = 0;
        v80 = 1;
        v67 = (struct _SECURITY_DESCRIPTOR *)hMem;
        Buffer = CLMString::GetBuffer((CLMString *)(a1 + 696), 0);
        InformationFileWrapper = CFileAccessor::BuildSD(
                                   (CFileAccessor *)a1,
                                   Buffer,
                                   v67,
                                   (struct _SECURITY_DESCRIPTOR **)&SecurityDescriptor);
        wil::details::out_param_t<wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
        if ( InformationFileWrapper < 0 )
          goto LABEL_182;
      }
      *(_DWORD *)(a1 + 920) = GetSecurityDescriptorLength(*v66);
LABEL_182:
      v69 = hMem;
      hMem = 0;
      if ( v69 )
        LocalFree(v69);
LABEL_184:
      if ( InformationFileWrapper >= 0 && (unsigned int)CFileAccessor::IsOplockBroken((CFileAccessor *)a1) )
        InformationFileWrapper = -2147024864;
      goto LABEL_187;
    }
    if ( InformationFileWrapper < 0 )
      goto LABEL_182;
    *(_QWORD *)RootPathName = 0;
    SecurityDescriptorSize = 0;
    p_hMem = (void **)RootPathName;
    SecurityDescriptor = 0;
    v80 = 1;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"D:(A;;FR;;;WD)(A;;FR;;;S-1-15-3-10)",
           1u,
           &SecurityDescriptor,
           &SecurityDescriptorSize) )
    {
      wil::details::out_param_t<wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
      pDacl[0] = 0;
    }
    else
    {
      InformationFileWrapper = ResultFromKnownLastError();
      wil::details::out_param_t<wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
      pDacl[0] = 0;
      if ( InformationFileWrapper < 0 )
        goto LABEL_150;
    }
    bDaclPresent[0] = 0;
    SecurityDescriptorSize = 0;
    if ( GetSecurityDescriptorDacl(
           *(PSECURITY_DESCRIPTOR *)RootPathName,
           bDaclPresent,
           pDacl,
           (LPBOOL)&SecurityDescriptorSize) )
    {
      InformationFileWrapper = 0;
    }
    else
    {
      InformationFileWrapper = ResultFromKnownLastError();
    }
LABEL_150:
    SecUtil::CSecurityDescriptor::CSecurityDescriptor(pAbsoluteSecurityDescriptor);
    if ( InformationFileWrapper < 0 )
    {
      dwBufferLength = 0;
    }
    else
    {
      try
      {
        SecUtil::CSecurityDescriptor::InitializeFromSelfRelative(pAbsoluteSecurityDescriptor, hMem);
        SecUtil::CSecurityDescriptor::SetDacl(
          (SecUtil::CSecurityDescriptor *)pAbsoluteSecurityDescriptor,
          v59,
          pDacl[0],
          v60);
      }
      catch ( ... )
      {
        indexer::result::details::result_from_caught_exception<1>(
          retaddr,
          1114,
          "onecoreuap\\base\\appmodel\\search\\mssph\\file\\fileacc.cxx");
      }
      dwBufferLength = 0;
      MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, 0, &dwBufferLength);
      v61 = GetLastError();
      if ( v61 != 122 )
      {
        if ( v61 > 0 )
          InformationFileWrapper = (unsigned __int16)v61 | 0x80070000;
        else
          InformationFileWrapper = v61;
      }
    }
    v62 = 0;
    if ( InformationFileWrapper < 0 )
      goto LABEL_161;
    v63 = LocalAlloc(0, dwBufferLength);
    v62 = v63;
    if ( !v63 )
    {
      InformationFileWrapper = -2147024882;
LABEL_161:
      if ( !v62 )
        goto LABEL_164;
      v64 = v62;
      goto LABEL_163;
    }
    if ( MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, v63, &dwBufferLength) )
    {
      InformationFileWrapper = 0;
    }
    else
    {
      InformationFileWrapper = ResultFromKnownLastError();
      if ( InformationFileWrapper < 0 )
        goto LABEL_161;
    }
    v64 = hMem;
    hMem = v62;
    if ( !v64 )
    {
LABEL_164:
      SecUtil::CSecurityDescriptor::~CSecurityDescriptor((SecUtil::CSecurityDescriptor *)pAbsoluteSecurityDescriptor);
      v65 = *(PSECURITY_DESCRIPTOR *)RootPathName;
      *(_QWORD *)RootPathName = 0;
      if ( v65 )
        LocalFree(v65);
      goto LABEL_166;
    }
LABEL_163:
    LocalFree(v64);
    goto LABEL_164;
  }
LABEL_187:
  if ( !*v86 && (unsigned __int64)(*(_QWORD *)(a1 + 104) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a1 + 104,
      -1);
  if ( InformationFileWrapper == 1251 )
  {
    InformationFileWrapper = -2147216890;
LABEL_192:
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssph\\\\file\\\\fileacc.cxx\"",
      (const wchar_t *)0x4AA,
      (unsigned int)L"[SrchCommon] CFileAccessor: Failed 0x%x",
      (const wchar_t *)(unsigned int)InformationFileWrapper);
    CFileAccessor::Reset((CFileAccessor *)a1);
    goto LABEL_193;
  }
  if ( InformationFileWrapper < 0 || InformationFileWrapper == 266755 )
    goto LABEL_192;
  if ( CFileAccessor::ShouldIndexEncryptedContent((CFileAccessor *)a1, 0) && *v81 != v71 )
    InformationFileWrapper = 266789;
LABEL_193:
  v97 = &TLMString<64,64,32767>::`vftable';
  CLMString::DeleteBuf((CLMString *)&v97, v100);
  return (unsigned int)InformationFileWrapper;
}

```

## disassembly

```asm
0x180003970  push    rbx
0x180003972  push    rsi
0x180003973  push    rdi
0x180003974  push    r12
0x180003976  push    r13
0x180003978  push    r14
0x18000397a  push    r15
0x18000397c  sub     rsp, 290h
0x180003983  mov     rax, cs:__security_cookie
0x18000398a  xor     rax, rsp
0x18000398d  mov     [rsp+2C8h+var_40], rax
0x180003995  mov     esi, r9d
0x180003998  mov     rbx, r8
0x18000399b  mov     r12, rdx
0x18000399e  mov     rdi, rcx
0x1800039a1  mov     [rsp+2C8h+var_228], rcx
0x1800039a9  mov     [rsp+2C8h+var_248], rbx
0x1800039b1  mov     dword ptr [rcx+358h], 1
0x1800039bb  lea     rax, [rcx+3A8h]
0x1800039c2  mov     [rsp+2C8h+var_230], rax
0x1800039ca  xor     r15d, r15d
0x1800039cd  mov     [rax], r15d
0x1800039d0  lea     rax, [rcx+90h]
0x1800039d7  mov     [rsp+2C8h+var_220], rax
0x1800039df  mov     [rax], r15d
0x1800039e2  mov     [rcx+94h], r15d
0x1800039e9  lea     rax, [rcx+3ACh]
0x1800039f0  mov     [rsp+2C8h+var_250], rax
0x1800039f5  mov     [rax], r15d
0x1800039f8  mov     [rcx+360h], r15
0x1800039ff  mov     [rcx+368h], r15
0x180003a06  mov     [rcx+370h], r15
0x180003a0d  mov     [rcx+378h], r15
0x180003a14  add     rcx, 3B0h; void *
0x180003a1b  xor     edx, edx; Val
0x180003a1d  mov     r8d, 250h; Size
0x180003a23  call    memset_0
0x180003a28  mov     rax, [rsp+2C8h+arg_20]
0x180003a30  mov     [rdi+380h], rax
0x180003a37  lea     rax, [rdi+35Ch]
0x180003a3e  mov     [rsp+2C8h+var_270], rax
0x180003a43  mov     [rax], esi
0x180003a45  mov     [rdi+58h], r15w
0x180003a4a  mov     [rdi+5Ah], r15b
0x180003a4e  mov     [rdi+5Ch], r15d
0x180003a52  mov     [rsp+2C8h+dwBufferLength], r15d
0x180003a57  lea     rax, [rsp+2C8h+var_D0]
0x180003a5f  mov     [rsp+2C8h+pszPath], rax
0x180003a67  mov     [rsp+2C8h+var_D8], 41h ; 'A'
0x180003a73  mov     [rsp+2C8h+var_D0], r15w
0x180003a7c  lea     rsi, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x180003a83  mov     [rsp+2C8h+var_E8], rsi
0x180003a8b  test    r12, r12
0x180003a8e  jnz     short loc_180003AE1
0x180003a90  mov     r14d, 80004003h
0x180003a96  mov     r12d, 0FFFFFFFFh
0x180003a9c  lea     r13, [rdi+2B8h]
0x180003aa3  mov     [rsp+2C8h+var_218], r13
0x180003aab  mov     rcx, [r13+8]; lpFileName
0x180003aaf  call    cs:__imp_GetFileAttributesW
0x180003ab5  cmp     eax, r12d
0x180003ab8  jz      loc_180003C67
0x180003abe  xor     edx, edx
0x180003ac0  mov     ecx, eax
0x180003ac2  call    cs:__imp_RtlIsPartialPlaceholder
0x180003ac8  test    al, al
0x180003aca  mov     rax, [rsp+2C8h+var_270]
0x180003acf  jz      loc_180003C6C
0x180003ad5  or      dword ptr [rax], 8
0x180003ad8  mov     byte ptr [rdi+59h], 1
0x180003adc  jmp     loc_180003C6C
0x180003ae1  lea     r8, [rdi+0F8h]
0x180003ae8  mov     rcx, r12
0x180003aeb  call    ??$ImportLMString@UIURL@@P81@EAAJQEA_WKPEAK@Z@@YAJPEAUIURL@@P80@EAAJQEA_WKPEAK@ZAEAVCLMString@@@Z; ImportLMString<IURL,long (IURL::*)(wchar_t * const,ulong,ulong *)>(IURL *,long (IURL::*)(wchar_t * const,ulong,ulong *),CLMString &)
0x180003af0  mov     r14d, eax
0x180003af3  test    eax, eax
0x180003af5  jnz     short loc_180003B13
0x180003af7  mov     rax, [r12]
0x180003afb  lea     rdx, [rdi+298h]
0x180003b02  mov     rcx, r12
0x180003b05  mov     rax, [rax+30h]
0x180003b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b0e  mov     r14d, eax
0x180003b11  jmp     short loc_180003B26
0x180003b13  lea     rdx, qword_18002A7A0; wchar_t *
0x180003b1a  lea     rcx, [rdi+0E0h]; this
0x180003b21  call    ?Init@CURL@@QEAAJPEB_WK@Z; CURL::Init(wchar_t const *,ulong)
0x180003b26  test    r14d, r14d
0x180003b29  js      loc_180003A96
0x180003b2f  lea     rdx, [rsp+2C8h+var_218]
0x180003b37  lea     rcx, [rdi+0E0h]
0x180003b3e  call    ?GetPath@CURL@@QEAA?AVCLMSubStr@@XZ; CURL::GetPath(void)
0x180003b43  mov     r9d, [rax+4]
0x180003b47  mov     edx, [rax]
0x180003b49  mov     rax, [rax+8]
0x180003b4d  mov     rcx, [rax+8]
0x180003b51  lea     rdx, [rcx+rdx*2]
0x180003b55  mov     rax, [rsp+2C8h+var_E8]
0x180003b5d  xor     r8d, r8d
0x180003b60  lea     rcx, [rsp+2C8h+var_E8]
0x180003b68  mov     rax, [rax+20h]
0x180003b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b71  lea     rcx, [rsp+2C8h+var_E8]; this
0x180003b79  call    ?ReplaceAll@CLMString@@QEAAX_W0I@Z; CLMString::ReplaceAll(wchar_t,wchar_t,uint)
0x180003b7e  mov     rax, [rdi+2B8h]
0x180003b85  mov     r12d, 0FFFFFFFFh
0x180003b8b  mov     r9d, r12d
0x180003b8e  xor     r8d, r8d
0x180003b91  mov     rdx, [rsp+2C8h+pszPath]
0x180003b99  lea     rcx, [rdi+2B8h]
0x180003ba0  mov     rax, [rax+20h]
0x180003ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ba9  lea     rcx, [rdi+2B8h]; this
0x180003bb0  call    ?ConvertLongPathName@@YAXAEAV?$TLMString@$0EA@$0EA@$0HPPP@@@@Z; ConvertLongPathName(TLMString<64,64,32767> &)
0x180003bb5  mov     rcx, [rsp+2C8h+pszPath]; pszPath
0x180003bbd  call    cs:__imp_PathGetDriveNumberW
0x180003bc3  mov     ecx, eax
0x180003bc5  cmp     eax, 0FFFFFFFFh
0x180003bc8  jz      short loc_180003C32
0x180003bca  mov     eax, dword ptr cs:asc_18002AC00+2; ":\\"
0x180003bd0  mov     dword ptr [rsp+2C8h+RootPathName+2], eax
0x180003bd7  movzx   eax, word ptr cs:asc_18002AC00+6; ""
0x180003bde  mov     [rsp+2C8h+RootPathName+6], ax
0x180003be6  add     cx, 41h ; 'A'
0x180003bea  mov     [rsp+2C8h+RootPathName], cx
0x180003bf2  lea     rcx, [rsp+2C8h+RootPathName]; lpRootPathName
0x180003bfa  call    cs:__imp_GetDriveTypeW
0x180003c00  mov     [rsp+2C8h+dwBufferLength], eax
0x180003c04  cmp     eax, 3
0x180003c07  jz      loc_180003A9C
0x180003c0d  cmp     eax, 2
0x180003c10  jnz     short loc_180003C27
0x180003c12  lea     rcx, POLID_DisableRemovableDriveIndexing
0x180003c19  call    cs:__imp_SHWindowsPolicy
0x180003c1f  test    eax, eax
0x180003c21  jz      loc_180003A9C
0x180003c27  mov     r14d, 80040D07h
0x180003c2d  jmp     loc_180003A9C
0x180003c32  mov     [rsp+2C8h+dwBufferLength], r15d
0x180003c37  xor     r9d, r9d; Context
0x180003c3a  xor     r8d, r8d; Parameter
0x180003c3d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180003c44  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180003c4b  call    cs:__imp_InitOnceExecuteOnce
0x180003c51  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, 0; bool g_isPerUserCatalogEnabled
0x180003c58  jz      short loc_180003C27
0x180003c5a  mov     [rsp+2C8h+dwBufferLength], 3
0x180003c62  jmp     loc_180003A9C
0x180003c67  mov     rax, [rsp+2C8h+var_270]
0x180003c6c  test    r14d, r14d
0x180003c6f  js      loc_180004782
0x180003c75  mov     esi, [rax]
0x180003c77  mov     rdx, [rsp+2C8h+pszPath]; wchar_t *
0x180003c7f  test    sil, 4
0x180003c83  jz      short loc_180003C92
0x180003c85  mov     rcx, rdi; this
0x180003c88  call    ?OpenHandleForReadingSD@CFileAccessor@@AEAAJPEB_W@Z; CFileAccessor::OpenHandleForReadingSD(wchar_t const *)
0x180003c8d  mov     r14d, eax
0x180003c90  jmp     short loc_180003CF3
0x180003c92  and     esi, 8
0x180003c95  mov     eax, 20080h
0x180003c9a  mov     ecx, 80000000h
0x180003c9f  cmovz   eax, ecx
0x180003ca2  mov     [rsp+2C8h+SecurityDescriptorSize], eax
0x180003ca6  mov     r8d, eax; unsigned int
0x180003ca9  mov     rcx, rdi; this
0x180003cac  call    ?OpenOplockedHandle@CFileAccessor@@AEAAJPEB_WK@Z; CFileAccessor::OpenOplockedHandle(wchar_t const *,ulong)
0x180003cb1  mov     r14d, eax
0x180003cb4  cmp     eax, 80041205h
0x180003cb9  jnz     short loc_180003CDC
0x180003cbb  test    esi, esi
0x180003cbd  jnz     short loc_180003CDC
0x180003cbf  mov     esi, 20080h
0x180003cc4  mov     r8d, esi; unsigned int
0x180003cc7  mov     rdx, [rsp+2C8h+pszPath]; wchar_t *
0x180003ccf  mov     rcx, rdi; this
0x180003cd2  call    ?OpenOplockedHandle@CFileAccessor@@AEAAJPEB_WK@Z; CFileAccessor::OpenOplockedHandle(wchar_t const *,ulong)
0x180003cd7  mov     r14d, eax
0x180003cda  jmp     short loc_180003CE0
0x180003cdc  mov     esi, [rsp+2C8h+SecurityDescriptorSize]
0x180003ce0  mov     eax, r15d
0x180003ce3  cmp     esi, 80000000h
0x180003ce9  setnz   al
0x180003cec  mov     rcx, [rsp+2C8h+var_250]
0x180003cf1  mov     [rcx], eax
0x180003cf3  test    r14d, r14d
0x180003cf6  js      loc_180004782
0x180003cfc  mov     rcx, rdi; this
0x180003cff  call    ?IsOplockBroken@CFileAccessor@@AEAAHXZ; CFileAccessor::IsOplockBroken(void)
0x180003d04  test    eax, eax
0x180003d06  jz      short loc_180003D13
0x180003d08  mov     r14d, 80070020h
0x180003d0e  jmp     loc_180004782
0x180003d13  mov     rcx, rdi; this
0x180003d16  call    ?CheckIfReparseTagAllowed@CFileAccessor@@AEAAJXZ; CFileAccessor::CheckIfReparseTagAllowed(void)
0x180003d1b  mov     r14d, eax
0x180003d1e  test    eax, eax
0x180003d20  js      loc_180004782
0x180003d26  xorps   xmm0, xmm0
0x180003d29  xor     eax, eax
0x180003d2b  movups  [rsp+2C8h+FileInformation], xmm0
0x180003d33  movups  [rsp+2C8h+var_1A8], xmm0
0x180003d3b  mov     [rsp+2C8h+var_198], rax
0x180003d43  mov     r9d, 28h ; '('; dwBufferSize
0x180003d49  lea     r8, [rsp+2C8h+FileInformation]; lpFileInformation
0x180003d51  xor     edx, edx; FileInformationClass
0x180003d53  mov     rcx, [rdi+68h]; hFile
0x180003d57  call    cs:__imp_GetFileInformationByHandleEx
0x180003d5d  test    eax, eax
0x180003d5f  jz      loc_180003EFF
0x180003d65  mov     edx, dword ptr [rsp+2C8h+FileInformation]
0x180003d6c  mov     [rdi+368h], edx
0x180003d72  mov     [rdi+3B4h], edx
0x180003d78  mov     ecx, dword ptr [rsp+2C8h+FileInformation+4]
0x180003d7f  mov     [rdi+36Ch], ecx
0x180003d85  mov     [rdi+3B8h], ecx
0x180003d8b  mov     eax, dword ptr [rsp+2C8h+FileInformation+8]
0x180003d92  mov     [rdi+370h], eax
0x180003d98  mov     [rdi+3BCh], eax
0x180003d9e  mov     eax, dword ptr [rsp+2C8h+FileInformation+0Ch]
0x180003da5  mov     [rdi+374h], eax
0x180003dab  mov     [rdi+3C0h], eax
0x180003db1  mov     rax, qword ptr [rsp+2C8h+var_1A8]
0x180003db9  mov     [rdi+360h], eax
0x180003dbf  mov     [rdi+3C4h], eax
0x180003dc5  mov     r8d, dword ptr [rsp+2C8h+var_1A8+4]
0x180003dcd  mov     [rdi+364h], r8d
0x180003dd4  mov     [rdi+3C8h], r8d
0x180003ddb  mov     r9, qword ptr [rsp+2C8h+var_1A8+8]
0x180003de3  test    r9, r9
0x180003de6  jnz     short loc_180003E09
0x180003de8  test    rax, rax
0x180003deb  jnz     short loc_180003DF5
0x180003ded  mov     [rdi+378h], edx
0x180003df3  jmp     short loc_180003E1A
0x180003df5  mov     [rdi+378h], eax
0x180003dfb  mov     [rdi+37Ch], r8d
0x180003e02  mov     edx, eax
0x180003e04  mov     rcx, r8
0x180003e07  jmp     short loc_180003E20
0x180003e09  mov     [rdi+378h], r9d
0x180003e10  mov     ecx, dword ptr [rsp+2C8h+var_1A8+0Ch]
0x180003e17  mov     edx, r9d
0x180003e1a  mov     [rdi+37Ch], ecx
0x180003e20  mov     rax, [rsp+2C8h+var_270]
0x180003e25  test    byte ptr [rax], 4
0x180003e28  jz      short loc_180003E58
0x180003e2a  shl     rcx, 20h
0x180003e2e  mov     eax, edx
0x180003e30  or      rcx, rax
0x180003e33  cmp     rcx, 1
0x180003e37  jb      short loc_180003E52
0x180003e39  lea     rax, [rcx-1]
0x180003e3d  mov     r14d, r15d
0x180003e40  mov     [rdi+378h], eax
0x180003e46  shr     rax, 20h
0x180003e4a  mov     [rdi+37Ch], eax
0x180003e50  jmp     short loc_180003E58
0x180003e52  mov     r14d, 80070216h
0x180003e58  mov     rdx, [rsp+2C8h+var_198]
0x180003e60  mov     rcx, [rdi+378h]
0x180003e67  mov     qword ptr [rsp+2C8h+bDaclPresent], rcx
0x180003e6c  mov     eax, ecx
0x180003e6e  mov     dword ptr [rsp+2C8h+hMem], ecx
0x180003e72  shr     rcx, 20h
0x180003e76  mov     dword ptr [rsp+2C8h+hMem+4], ecx
0x180003e7a  mov     ecx, edx
0x180003e7c  shr     rcx, 2
0x180003e80  and     ecx, 8
0x180003e83  mov     eax, edx
0x180003e85  and     eax, 7
0x180003e88  or      rcx, rax
0x180003e8b  mov     rax, [rsp+2C8h+hMem]
0x180003e90  add     rax, rcx
0x180003e93  mov     [rsp+2C8h+hMem], rax
0x180003e98  mov     ecx, dword ptr [rsp+2C8h+hMem]
0x180003e9c  mov     [rsp+2C8h+bDaclPresent], ecx
0x180003ea0  shr     rax, 20h
0x180003ea4  mov     [rsp+2C8h+bDaclPresent+4], eax
0x180003ea8  mov     rax, qword ptr [rsp+2C8h+bDaclPresent]
0x180003ead  mov     [rdi+378h], rax
0x180003eb4  lea     rsi, [rdi+388h]
0x180003ebb  mov     [rsi], edx
0x180003ebd  mov     [rdi+3B0h], edx
0x180003ec3  mov     eax, [rdi+5Ch]
0x180003ec6  mov     [rdi+3D4h], eax
0x180003ecc  test    r14d, r14d
0x180003ecf  js      short loc_180003EDD
0x180003ed1  bt      edx, 0Ah
0x180003ed5  jnb     short loc_180003EE3
0x180003ed7  cmp     byte ptr [rdi+58h], 0
0x180003edb  jz      short loc_180003EE9
0x180003edd  bt      edx, 0Ah
0x180003ee1  jb      short loc_180003F19
0x180003ee3  cmp     byte ptr [rdi+58h], 0
0x180003ee7  jz      short loc_180003F19
0x180003ee9  mov     rcx, rdi; this
0x180003eec  call    ?CheckIfReparseTagAllowed@CFileAccessor@@AEAAJXZ; CFileAccessor::CheckIfReparseTagAllowed(void)
0x180003ef1  mov     r14d, eax
0x180003ef4  mov     eax, [rdi+5Ch]
  ... truncated ...
```
