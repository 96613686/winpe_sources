# CFolderAclEngine::_IsItemPrivate(IShellItem *,int *)

- ea: `0x18000c6f0`
- end: `0x18000d1dc`
- name: `?_IsItemPrivate@CFolderAclEngine@@IEAAJPEAUIShellItem@@PEAH@Z`
- size: `2796`
- prototype: `__int64 __fastcall(CFolderAclEngine *__hidden this, struct IShellItem *, int *)`
- caller_count: `1`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001a3b0`

## callees

- `0x1800096a0`
- `0x1800098dc`
- `0x18000a5f8`
- `0x18000bc00`
- `0x18000c6f0`
- `0x18000d1f0`
- `0x18000dd60`
- `0x18000f4b0`
- `0x18000f7a0`
- `0x18000f7f0`
- `0x18000fb00`
- `0x1800127e0`
- `0x180012b1c`
- `0x18001d2d0`
- `0x1800254e0`
- `0x1800259bc`
- `0x18002a960`
- `0x18005e1c8`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ccdf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cd13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ccdf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cd13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cffe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cffe`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000cf6f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000cf6f`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000ced8`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000ced8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000ce92`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000ce92`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000cab7`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000cab7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000cd70`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000cd70`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000cd46`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000d119`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000cd46`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000d119`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cd59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cd59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cad2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cff3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cad2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cff3`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x18000c898`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x18000c898`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000d0d0`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000d0d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c915`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c915`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbb2`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18000c9b2`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18000c9b2`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000c834`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000c834`
- `ntdll!RtlMapGenericMask` at `0x18000cdad`
- `ntdll!RtlMapGenericMask` at `0x18000cdad`
- `SHCORE!SHStrDupW` at `0x18000c907`
- `SHCORE!SHStrDupW` at `0x18000c907`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x18000c929`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x18000c929`
- `SHLWAPI!PathStripToRootW` at `0x18000c97a`
- `SHLWAPI!PathStripToRootW` at `0x18000c97a`
- `SHLWAPI!StrChrW` at `0x18000d063`
- `SHLWAPI!StrChrW` at `0x18000d087`
- `SHLWAPI!StrChrW` at `0x18000d063`
- `SHLWAPI!StrChrW` at `0x18000d087`
- `SHLWAPI!PathRemoveBackslashW` at `0x18000c8f0`
- `SHLWAPI!PathRemoveBackslashW` at `0x18000c8f0`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18000ca18`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18000ca18`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFolderAclEngine::_IsItemPrivate(CFolderAclEngine *this, struct IShellItem *a2, int *a3)
{
  int *v3; // r14
  CAceList *v4; // r13
  int NonSystemAceList; // r12d
  int v6; // ebx
  __int64 v7; // rbx
  __int64 v8; // rdi
  WCHAR *v9; // rsi
  __int64 v10; // rcx
  WCHAR *v11; // rdx
  __int64 v12; // r8
  WCHAR *v13; // r9
  WCHAR v14; // ax
  WCHAR *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  WCHAR *v18; // r8
  WCHAR v19; // cx
  WCHAR *v20; // rcx
  HRESULT v21; // esi
  const WCHAR *v22; // rcx
  LPWSTR v23; // rcx
  WCHAR *v24; // rdx
  WCHAR v25; // ax
  WCHAR *v26; // rcx
  struct CAceList *v27; // rbx
  int v28; // edi
  signed int NamedSecurityInfoW; // eax
  unsigned int v30; // edx
  int v31; // r8d
  WCHAR *v32; // r15
  struct _ACL *v33; // r14
  _QWORD *v34; // rsi
  unsigned int v35; // edx
  int Error; // edi
  DWORD v37; // r13d
  BOOL v38; // esi
  CAceList *v39; // rbx
  int i; // r14d
  int *v41; // rdi
  int v42; // eax
  int j; // r14d
  int *v44; // rdi
  int v45; // eax
  LPWSTR v46; // rcx
  FARPROC v48; // rax
  struct CAce *v49; // rdi
  FARPROC ProcAddress; // rax
  struct CAce *v51; // rdi
  HMODULE v52; // rcx
  HMODULE v53; // rcx
  DWORD v54; // r13d
  HLOCAL v55; // rax
  void *v56; // r14
  unsigned int v57; // eax
  DWORD v58; // eax
  __int64 v59; // rcx
  int v60; // eax
  __int64 v61; // rdi
  __int64 (__fastcall *v62)(__int64, __int64, DWORD *); // rax
  int v63; // eax
  char *v64; // r14
  DWORD *v65; // rax
  DWORD *v66; // rbx
  char *v67; // r15
  signed int LastError; // eax
  const WCHAR *v69; // r15
  PWSTR v70; // rax
  const unsigned __int16 *v71; // r14
  const WCHAR *v72; // rsi
  PWSTR v73; // rax
  const WCHAR *v74; // rax
  CShareCache *v75; // rcx
  DWORD LengthSid; // eax
  WORD pControl[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v78; // [rsp+44h] [rbp-BCh]
  CAceList *v79; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v80; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  DWORD FileSystemFlags[2]; // [rsp+60h] [rbp-A0h] BYREF
  int *v83; // [rsp+68h] [rbp-98h]
  LPWSTR ppwsz; // [rsp+70h] [rbp-90h] BYREF
  PCWSTR ppszServer; // [rsp+78h] [rbp-88h] BYREF
  CAceList *v86; // [rsp+80h] [rbp-80h] BYREF
  PACL v87; // [rsp+88h] [rbp-78h]
  LPVOID pAce; // [rsp+90h] [rbp-70h] BYREF
  PACL ppDacl; // [rsp+98h] [rbp-68h] BYREF
  PCWSTR v90; // [rsp+A0h] [rbp-60h]
  PSID ppsidOwner; // [rsp+A8h] [rbp-58h] BYREF
  LPWSTR v92; // [rsp+B0h] [rbp-50h]
  __int64 pAclInformation; // [rsp+B8h] [rbp-48h] BYREF
  int v94; // [rsp+C0h] [rbp-40h]
  WCHAR psz[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR pszPath[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v3 = a3;
  v83 = a3;
  v4 = (CAceList *)a2;
  v86 = (CAceList *)a2;
  *a3 = 0;
  ppwsz = 0;
  pv = 0;
  v79 = 0;
  *(_QWORD *)FileSystemFlags = 0;
  if ( ((int (__fastcall *)(struct IShellItem *, _QWORD, const GUID *, GUID *, DWORD *))a2->lpVtbl->BindToHandler)(
         a2,
         0,
         &BHID_SFObject,
         &GUID_7d903fca_d6f9_4810_8332_946c0177e247,
         FileSystemFlags) >= 0 )
  {
    v80 = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)FileSystemFlags + 32LL))(
           *(_QWORD *)FileSystemFlags,
           &v80);
    if ( v6 >= 0 )
    {
      v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, CAceList **))v80)(
             v80,
             &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
             &v79);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    }
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)FileSystemFlags + 16LL))(*(_QWORD *)FileSystemFlags);
    if ( v6 >= 0 )
      goto LABEL_7;
  }
  NonSystemAceList = (**(__int64 (__fastcall ***)(CAceList *, GUID *, CAceList **))v4)(
                       v4,
                       &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                       &v79);
  if ( NonSystemAceList >= 0 )
  {
LABEL_7:
    NonSystemAceList = (*(__int64 (__fastcall **)(CAceList *, __int64, LPVOID *))(*(_QWORD *)v79 + 40LL))(
                         v79,
                         2147844096LL,
                         &pv);
    (*(void (__fastcall **)(CAceList *))(*(_QWORD *)v79 + 16LL))(v79);
  }
  v7 = 2147483646;
  v8 = 260;
  if ( NonSystemAceList < 0 )
    goto LABEL_66;
  v9 = (WCHAR *)pv;
  psz[0] = 0;
  InitOnceExecuteOnce(&InitOnce, OneTimeInit, 0, 0);
  v10 = 2147483646;
  v11 = v9;
  v12 = 260;
  v13 = pszPath;
  do
  {
    if ( !v10 )
      break;
    v14 = *v11;
    if ( !*v11 )
      break;
    ++v11;
    *v13++ = v14;
    --v10;
    --v12;
  }
  while ( v12 );
  v15 = v13 - 1;
  if ( v12 )
    v15 = v13;
  *v15 = 0;
  if ( !v12 )
    goto LABEL_157;
  ppszServer = 0;
  if ( !PathIsUNCEx(pszPath, &ppszServer) )
    goto LABEL_17;
  v69 = ppszServer;
  v70 = StrChrW(ppszServer, 0x5Cu);
  if ( !v70 )
    goto LABEL_17;
  *v70 = 0;
  v71 = v70 + 1;
  if ( !v70[1] )
  {
    v3 = v83;
LABEL_17:
    v16 = 2147483646;
    v17 = 260;
    v18 = psz;
    do
    {
      if ( !v16 )
        break;
      v19 = *v9;
      if ( !*v9 )
        break;
      ++v9;
      *v18++ = v19;
      --v16;
      --v17;
    }
    while ( v17 );
    v20 = v18 - 1;
    if ( v17 )
      v20 = v18;
    *v20 = 0;
    v21 = -2147024774;
    if ( v17 )
    {
      v21 = 0;
      PathRemoveBackslashW(psz);
    }
    goto LABEL_25;
  }
  v72 = 0;
  v73 = StrChrW(v70 + 1, 0x5Cu);
  if ( v73 )
  {
    *v73 = 0;
    v74 = v73 + 1;
    if ( *v74 )
      v72 = v74;
  }
  if ( !(unsigned int)SHIsThisComputerByNameOnly(v69) || !CShareCache::IsExistingShare(v75, v71, psz, 260) )
  {
    v3 = v83;
    goto LABEL_157;
  }
  if ( !v72 )
  {
    v3 = v83;
    goto LABEL_26;
  }
  v21 = PathCchAppend(psz, 0x104u, v72);
  v3 = v83;
LABEL_25:
  if ( v21 )
  {
LABEL_157:
    v22 = (const WCHAR *)pv;
    ppwsz = (LPWSTR)pv;
    goto LABEL_28;
  }
LABEL_26:
  NonSystemAceList = SHStrDupW(psz, &ppwsz);
  CoTaskMemFree(pv);
  if ( NonSystemAceList < 0 )
    goto LABEL_66;
  v22 = ppwsz;
LABEL_28:
  if ( PathIsNetworkPathW(v22) )
    goto LABEL_66;
  v23 = ppwsz;
  v24 = psz;
  do
  {
    if ( !v7 )
      break;
    v25 = *v23;
    if ( !*v23 )
      break;
    ++v23;
    *v24++ = v25;
    --v7;
    --v8;
  }
  while ( v8 );
  v26 = v24 - 1;
  if ( v8 )
    v26 = v24;
  *v26 = 0;
  if ( !v8 )
    goto LABEL_66;
  if ( !PathStripToRootW(psz) )
    goto LABEL_66;
  FileSystemFlags[0] = 0;
  if ( !GetVolumeInformationW(psz, 0, 0, 0, 0, FileSystemFlags, 0, 0) || (FileSystemFlags[0] & 8) == 0 )
    goto LABEL_66;
  v27 = 0;
  v79 = 0;
  v28 = (int)ppwsz;
  v92 = ppwsz;
  ppszServer = 0;
  ppDacl = 0;
  ppsidOwner = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(
                         ppwsz,
                         SE_FILE_OBJECT,
                         5u,
                         &ppsidOwner,
                         0,
                         &ppDacl,
                         0,
                         (PSECURITY_DESCRIPTOR *)&ppszServer);
  NonSystemAceList = NamedSecurityInfoW;
  if ( NamedSecurityInfoW > 0 )
    NonSystemAceList = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
  if ( NonSystemAceList < 0 )
    goto LABEL_161;
  v32 = (WCHAR *)ppszServer;
  v90 = ppszServer;
  v33 = ppDacl;
  v87 = ppDacl;
  NonSystemAceList = -2147024882;
  v34 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  pAce = v34;
  if ( v34 )
  {
    *v34 = 0;
    v34[1] = 0;
    v34[2] = 0;
    v34[3] = 1;
    Error = CAceList::_Init((CAceList *)v34);
    if ( Error >= 0 && v33 )
    {
      pAclInformation = 0;
      v94 = 0;
      GetAclInformation(v33, &pAclInformation, 0xCu, AclSizeInformation);
      v37 = 0;
      LODWORD(v80) = 0;
      while ( 1 )
      {
        if ( v37 >= (unsigned int)pAclInformation )
        {
LABEL_112:
          v4 = v86;
          v32 = (WCHAR *)v90;
          v27 = v79;
          break;
        }
        pAce = 0;
        if ( !GetAce(v33, v37, &pAce) )
        {
          Error = ResultFromKnownLastError();
          goto LABEL_111;
        }
        v64 = (char *)pAce;
        Error = -2147024882;
        v65 = (DWORD *)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
        v66 = v65;
        pv = v65;
        if ( !v65 )
          goto LABEL_110;
        *(_QWORD *)v65 = 0x80000;
        *((_QWORD *)v65 + 1) = 0;
        *((_QWORD *)v65 + 2) = 0;
        *((_QWORD *)v65 + 3) = 0;
        if ( !v64 )
        {
          Error = -2147024809;
LABEL_134:
          CAce::`scalar deleting destructor'((CAce *)v66, v35);
          goto LABEL_110;
        }
        v67 = v64 + 8;
        v78 = *v64;
        if ( v78 == 9 )
        {
          LengthSid = GetLengthSid(v64 + 8);
          Error = CAce::_Init(
                    (CAce *)v66,
                    v64 + 8,
                    *((_DWORD *)v64 + 1),
                    v64[1],
                    *v64,
                    *((_WORD *)v64 + 1),
                    &v67[LengthSid]);
        }
        else
        {
          Error = -2147024809;
          if ( v64 != (char *)-8LL )
          {
            LOWORD(FileSystemFlags[0]) = *((_WORD *)v64 + 1);
            LOBYTE(pControl[0]) = v64[1];
            LODWORD(pv) = *((_DWORD *)v64 + 1);
            if ( IsValidSid(v64 + 8) )
            {
              v54 = GetLengthSid(v64 + 8);
              Error = -2147024882;
              v55 = LocalAlloc(0x40u, v54);
              v56 = v55;
              if ( v55 )
              {
                if ( CopySid(v54, v55, v67) )
                {
                  Error = 0;
LABEL_93:
                  *((_QWORD *)v66 + 1) = v56;
                  *(_BYTE *)v66 = v78;
                  *((_BYTE *)v66 + 1) = pControl[0];
                  *((_WORD *)v66 + 1) = FileSystemFlags[0];
                  v66[1] = (unsigned int)pv;
                  RtlMapGenericMask(v66 + 1, (PGENERIC_MAPPING)&GenericMapping);
                  v66[7] = 0x80000000;
                  if ( !*(_BYTE *)v66 || (v57 = 0x80000000, *(_BYTE *)v66 == 9) )
                  {
                    v66[7] = -2147483647;
                    v57 = -2147483647;
                  }
                  if ( (*((_BYTE *)v66 + 1) & 0x10) != 0 )
                    v66[7] = v57 | 0x20;
                }
                else
                {
                  Error = ResultFromKnownLastError();
                  if ( Error >= 0 )
                    goto LABEL_93;
                  LocalFree(v56);
                }
              }
            }
            v37 = v80;
          }
        }
        if ( Error < 0 )
          goto LABEL_134;
        v58 = v66[7];
        v59 = v58 & 0x20;
        if ( (v58 & 0x20) != 0 )
        {
          v60 = v58 & 1;
        }
        else
        {
          v60 = v58 & 1;
          if ( !v60 )
          {
            Error = CAceList::_AddExplicitAceToDpa(v59, v34, v66);
            goto LABEL_109;
          }
        }
        if ( !(_DWORD)v59 && v60 )
        {
          Error = CAceList::_AddExplicitAceToDpa(v59, v34 + 1, v66);
        }
        else
        {
          v61 = v34[2];
          v62 = (__int64 (__fastcall *)(__int64, __int64, DWORD *))qword_1800959F8;
          if ( qword_1800959F8 == -1 )
          {
            GetProcFromComCtl32(&qword_1800959F8, 334);
            v62 = (__int64 (__fastcall *)(__int64, __int64, DWORD *))qword_1800959F8;
          }
          if ( v62 )
            v63 = v62(v61, 0x7FFFFFFF, v66);
          else
            v63 = -1;
          Error = 0;
          if ( v63 == -1 )
            Error = -2147024882;
        }
LABEL_109:
        if ( Error )
          goto LABEL_134;
LABEL_110:
        v33 = v87;
LABEL_111:
        LODWORD(v80) = ++v37;
        if ( Error < 0 )
          goto LABEL_112;
      }
    }
    NonSystemAceList = Error;
    if ( Error >= 0 && v32 )
    {
      pControl[0] = 0;
      LODWORD(pv) = 0;
      if ( GetSecurityDescriptorControl(v32, pControl, (LPDWORD)&pv) )
      {
        if ( (pControl[0] & 0x1000) != 0 )
          *((_DWORD *)v34 + 6) = 0;
        *((_DWORD *)v34 + 7) = 0;
LABEL_119:
        v27 = (struct CAceList *)v34;
        v79 = (CAceList *)v34;
        goto LABEL_46;
      }
      LastError = GetLastError();
      NonSystemAceList = LastError;
      if ( LastError > 0 )
        NonSystemAceList = (unsigned __int16)LastError | 0x80070000;
    }
    if ( NonSystemAceList < 0 )
    {
      CAceList::`scalar deleting destructor'((CAceList *)v34, v35);
      goto LABEL_46;
    }
    goto LABEL_119;
  }
LABEL_46:
  LocalFree((HLOCAL)ppszServer);
  if ( NonSystemAceList >= 0 )
  {
    v86 = 0;
    LODWORD(v80) = 0;
    v38 = (*(int (__fastcall **)(CAceList *, __int64, __int64 *))(*(_QWORD *)v4 + 48LL))(v4, 1614807040, &v80) >= 0
       && (_DWORD)v80 == 1610612736;
    NonSystemAceList = CFolderAclEngine::_s_GetNonSystemAceList(v27, v38, &v86);
    v39 = v86;
    if ( NonSystemAceList < 0 || CAceList::DoesAceListHasMoreThanOneSidForAllow(v86) )
      goto LABEL_61;
    for ( i = 0; ; ++i )
    {
      v41 = (int *)*((_QWORD *)v39 + 1);
      if ( v41 )
        v42 = *v41;
      else
        v42 = 0;
      if ( i >= v42 )
      {
        for ( j = 0; ; ++j )
        {
          v44 = (int *)*((_QWORD *)v39 + 2);
          if ( v44 )
            v45 = *v44;
          else
            v45 = 0;
          if ( j >= v45 )
          {
            *v83 = 1;
            goto LABEL_61;
          }
          ProcAddress = (FARPROC)qword_180095A20;
          if ( qword_180095A20 == (__int64 (__fastcall *)(_QWORD, _QWORD))-1LL )
          {
            v53 = g_hinstCC;
            if ( !g_hinstCC )
            {
              DelayLoadCC();
              v53 = g_hinstCC;
              if ( !g_hinstCC )
              {
                qword_180095A20 = 0;
LABEL_89:
                v51 = 0;
                goto LABEL_77;
              }
            }
            ProcAddress = GetProcAddress(v53, (LPCSTR)0x14C);
            qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))ProcAddress;
          }
          if ( !ProcAddress )
            goto LABEL_89;
          v51 = (struct CAce *)((__int64 (__fastcall *)(int *, _QWORD))ProcAddress)(v44, j);
LABEL_77:
          if ( !(unsigned int)CFolderAclEngine::_s_IsSystemAce(v51, v38) && !(unsigned int)CAce::IsUser(v51) )
            goto LABEL_61;
        }
      }
      v48 = (FARPROC)qword_180095A20;
      if ( qword_180095A20 == (__int64 (__fastcall *)(_QWORD, _QWORD))-1LL )
      {
        v52 = g_hinstCC;
        if ( !g_hinstCC )
        {
          DelayLoadCC();
          v52 = g_hinstCC;
          if ( !g_hinstCC )
          {
            qword_180095A20 = 0;
LABEL_87:
            v49 = 0;
            goto LABEL_71;
          }
        }
        v48 = GetProcAddress(v52, (LPCSTR)0x14C);
        qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))v48;
      }
      if ( !v48 )
        goto LABEL_87;
      v49 = (struct CAce *)((__int64 (__fastcall *)(int *, _QWORD))v48)(v41, i);
LABEL_71:
      if ( !(unsigned int)CFolderAclEngine::_s_IsSystemAce(v49, v38) && !(unsigned int)CAce::IsUser(v49) )
      {
LABEL_61:
        if ( v39 )
          CAceList::`scalar deleting destructor'(v39, v30);
        v27 = v79;
        goto LABEL_64;
      }
    }
  }
  v28 = (int)v92;
  v3 = v83;
LABEL_161:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v31, v28, NonSystemAceList);
  if ( NonSystemAceList == -2147024891 )
  {
    NonSystemAceList = 0;
    *v3 = 0;
  }
LABEL_64:
  if ( v27 )
    CAceList::`scalar deleting destructor'(v27, v30);
LABEL_66:
  v46 = ppwsz;
  ppwsz = 0;
  CoTaskMemFree(v46);
  return (unsigned int)NonSystemAceList;
}

```

## disassembly

```asm
0x18000c6f0  mov     [rsp-8+arg_0], rbx
0x18000c6f5  push    rbp
0x18000c6f6  push    rsi
0x18000c6f7  push    rdi
0x18000c6f8  push    r12
0x18000c6fa  push    r13
0x18000c6fc  push    r14
0x18000c6fe  push    r15
0x18000c700  lea     rbp, [rsp-400h]
0x18000c708  sub     rsp, 500h
0x18000c70f  mov     rax, cs:__security_cookie
0x18000c716  xor     rax, rsp
0x18000c719  mov     [rbp+430h+var_40], rax
0x18000c720  mov     r14, r8
0x18000c723  mov     [rsp+530h+var_4C8], r8
0x18000c728  mov     r13, rdx
0x18000c72b  mov     [rbp+430h+var_4B0], rdx
0x18000c72f  xor     r15d, r15d
0x18000c732  mov     [r8], r15d
0x18000c735  mov     [rsp+530h+ppwsz], r15
0x18000c73a  mov     [rsp+530h+pv], r15
0x18000c73f  mov     [rsp+530h+var_4E8], r15
0x18000c744  mov     qword ptr [rsp+530h+FileSystemFlags], r15
0x18000c749  mov     rax, [rdx]
0x18000c74c  lea     rcx, [rsp+530h+FileSystemFlags]
0x18000c751  mov     [rsp+530h+lpMaximumComponentLength], rcx
0x18000c756  lea     r9, _GUID_7d903fca_d6f9_4810_8332_946c0177e247
0x18000c75d  lea     r8, BHID_SFObject
0x18000c764  xor     edx, edx
0x18000c766  mov     rcx, r13
0x18000c769  mov     rax, [rax+18h]
0x18000c76d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c772  test    eax, eax
0x18000c774  jns     short loc_18000C79A
0x18000c776  mov     rax, [r13+0]
0x18000c77a  lea     r8, [rsp+530h+var_4E8]
0x18000c77f  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18000c786  mov     rcx, r13
0x18000c789  mov     rax, [rax]
0x18000c78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c791  mov     r12d, eax
0x18000c794  test    eax, eax
0x18000c796  js      short loc_18000C803
0x18000c798  jmp     short loc_18000C7D4
0x18000c79a  mov     [rsp+530h+var_4E0], r15
0x18000c79f  mov     rcx, qword ptr [rsp+530h+FileSystemFlags]
0x18000c7a4  mov     rax, [rcx]
0x18000c7a7  lea     rdx, [rsp+530h+var_4E0]
0x18000c7ac  mov     rax, [rax+20h]
0x18000c7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7b5  mov     ebx, eax
0x18000c7b7  test    eax, eax
0x18000c7b9  jns     loc_18000CC89
0x18000c7bf  mov     rcx, qword ptr [rsp+530h+FileSystemFlags]
0x18000c7c4  mov     rax, [rcx]
0x18000c7c7  mov     rax, [rax+10h]
0x18000c7cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7d0  test    ebx, ebx
0x18000c7d2  js      short loc_18000C776
0x18000c7d4  mov     rcx, [rsp+530h+var_4E8]
0x18000c7d9  mov     rax, [rcx]
0x18000c7dc  lea     r8, [rsp+530h+pv]
0x18000c7e1  mov     edx, 80058000h
0x18000c7e6  mov     rax, [rax+28h]
0x18000c7ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7ef  mov     r12d, eax
0x18000c7f2  mov     rcx, [rsp+530h+var_4E8]
0x18000c7f7  mov     rax, [rcx]
0x18000c7fa  mov     rax, [rax+10h]
0x18000c7fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c803  mov     ebx, 7FFFFFFEh
0x18000c808  mov     edi, 104h
0x18000c80d  test    r12d, r12d
0x18000c810  js      loc_18000CBA8
0x18000c816  mov     rsi, [rsp+530h+pv]
0x18000c81b  mov     [rbp+430h+psz], r15w
0x18000c820  xor     r9d, r9d; Context
0x18000c823  xor     r8d, r8d; Parameter
0x18000c826  lea     rdx, _OneTimeInit; InitFn
0x18000c82d  lea     rcx, InitOnce; InitOnce
0x18000c834  call    cs:__imp_InitOnceExecuteOnce
0x18000c83a  mov     ecx, ebx
0x18000c83c  mov     rdx, rsi
0x18000c83f  mov     r8d, edi
0x18000c842  lea     r9, [rbp+430h+pszPath]
0x18000c849  nop     dword ptr [rax+00000000h]
0x18000c850  test    rcx, rcx
0x18000c853  jz      short loc_18000C872
0x18000c855  movzx   eax, word ptr [rdx]
0x18000c858  test    ax, ax
0x18000c85b  jz      short loc_18000C872
0x18000c85d  add     rdx, 2
0x18000c861  mov     [r9], ax
0x18000c865  add     r9, 2
0x18000c869  dec     rcx
0x18000c86c  sub     r8, 1
0x18000c870  jnz     short loc_18000C850
0x18000c872  lea     rcx, [r9-2]
0x18000c876  test    r8, r8
0x18000c879  cmovnz  rcx, r9
0x18000c87d  mov     [rcx], r15w
0x18000c881  jz      loc_18000D107
0x18000c887  mov     [rsp+530h+ppszServer], r15
0x18000c88c  lea     rdx, [rsp+530h+ppszServer]; ppszServer
0x18000c891  lea     rcx, [rbp+430h+pszPath]; pszPath
0x18000c898  call    cs:__imp_PathIsUNCEx
0x18000c89e  test    eax, eax
0x18000c8a0  jnz     loc_18000D056
0x18000c8a6  mov     rax, rbx
0x18000c8a9  mov     rdx, rdi
0x18000c8ac  lea     r8, [rbp+430h+psz]
0x18000c8b0  test    rax, rax
0x18000c8b3  jz      short loc_18000C8D2
0x18000c8b5  movzx   ecx, word ptr [rsi]
0x18000c8b8  test    cx, cx
0x18000c8bb  jz      short loc_18000C8D2
0x18000c8bd  add     rsi, 2
0x18000c8c1  mov     [r8], cx
0x18000c8c5  add     r8, 2
0x18000c8c9  dec     rax
0x18000c8cc  sub     rdx, 1
0x18000c8d0  jnz     short loc_18000C8B0
0x18000c8d2  lea     rcx, [r8-2]
0x18000c8d6  test    rdx, rdx
0x18000c8d9  cmovnz  rcx, r8
0x18000c8dd  mov     [rcx], r15w
0x18000c8e1  mov     esi, 8007007Ah
0x18000c8e6  cmovnz  esi, r15d
0x18000c8ea  jz      short loc_18000C8F6
0x18000c8ec  lea     rcx, [rbp+430h+psz]; pszPath
0x18000c8f0  call    cs:__imp_PathRemoveBackslashW
0x18000c8f6  test    esi, esi
0x18000c8f8  jnz     loc_18000D107
0x18000c8fe  lea     rdx, [rsp+530h+ppwsz]; ppwsz
0x18000c903  lea     rcx, [rbp+430h+psz]; psz
0x18000c907  call    cs:__imp_SHStrDupW
0x18000c90d  mov     r12d, eax
0x18000c910  mov     rcx, [rsp+530h+pv]; pv
0x18000c915  call    cs:__imp_CoTaskMemFree
0x18000c91b  test    r12d, r12d
0x18000c91e  js      loc_18000CBA8
0x18000c924  mov     rcx, [rsp+530h+ppwsz]; pszPath
0x18000c929  call    cs:__imp_PathIsNetworkPathW
0x18000c92f  test    eax, eax
0x18000c931  jnz     loc_18000CBA8
0x18000c937  mov     rcx, [rsp+530h+ppwsz]
0x18000c93c  lea     rdx, [rbp+430h+psz]
0x18000c940  test    rbx, rbx
0x18000c943  jz      short loc_18000C961
0x18000c945  movzx   eax, word ptr [rcx]
0x18000c948  test    ax, ax
0x18000c94b  jz      short loc_18000C961
0x18000c94d  add     rcx, 2
0x18000c951  mov     [rdx], ax
0x18000c954  add     rdx, 2
0x18000c958  dec     rbx
0x18000c95b  sub     rdi, 1
0x18000c95f  jnz     short loc_18000C940
0x18000c961  lea     rcx, [rdx-2]
0x18000c965  test    rdi, rdi
0x18000c968  cmovnz  rcx, rdx
0x18000c96c  mov     [rcx], r15w
0x18000c970  jz      loc_18000CBA8
0x18000c976  lea     rcx, [rbp+430h+psz]; pszPath
0x18000c97a  call    cs:__imp_PathStripToRootW
0x18000c980  test    eax, eax
0x18000c982  jz      loc_18000CBA8
0x18000c988  mov     [rsp+530h+FileSystemFlags], r15d
0x18000c98d  mov     [rsp+530h+nFileSystemNameSize], r15d; nFileSystemNameSize
0x18000c992  mov     [rsp+530h+lpFileSystemNameBuffer], r15; lpFileSystemNameBuffer
0x18000c997  lea     rax, [rsp+530h+FileSystemFlags]
0x18000c99c  mov     [rsp+530h+lpFileSystemFlags], rax; lpFileSystemFlags
0x18000c9a1  mov     [rsp+530h+lpMaximumComponentLength], r15; lpMaximumComponentLength
0x18000c9a6  xor     r9d, r9d; lpVolumeSerialNumber
0x18000c9a9  xor     r8d, r8d; nVolumeNameSize
0x18000c9ac  xor     edx, edx; lpVolumeNameBuffer
0x18000c9ae  lea     rcx, [rbp+430h+psz]; lpRootPathName
0x18000c9b2  call    cs:__imp_GetVolumeInformationW
0x18000c9b8  test    eax, eax
0x18000c9ba  jz      loc_18000CBA8
0x18000c9c0  test    byte ptr [rsp+530h+FileSystemFlags], 8
0x18000c9c5  jz      loc_18000CBA8
0x18000c9cb  mov     rbx, r15
0x18000c9ce  mov     [rsp+530h+var_4E8], rbx
0x18000c9d3  mov     rdi, [rsp+530h+ppwsz]
0x18000c9d8  mov     [rbp+430h+var_480], rdi
0x18000c9dc  mov     [rsp+530h+ppszServer], r15
0x18000c9e1  mov     [rbp+430h+ppDacl], r15
0x18000c9e5  mov     [rbp+430h+ppsidOwner], r15
0x18000c9e9  lea     rax, [rsp+530h+ppszServer]
0x18000c9ee  mov     qword ptr [rsp+530h+nFileSystemNameSize], rax; ppSecurityDescriptor
0x18000c9f3  mov     [rsp+530h+lpFileSystemNameBuffer], r15; ppSacl
0x18000c9f8  lea     rax, [rbp+430h+ppDacl]
0x18000c9fc  mov     [rsp+530h+lpFileSystemFlags], rax; ppDacl
0x18000ca01  mov     [rsp+530h+lpMaximumComponentLength], r15; ppsidGroup
0x18000ca06  lea     r9, [rbp+430h+ppsidOwner]; ppsidOwner
0x18000ca0a  mov     edx, 1; ObjectType
0x18000ca0f  mov     r8d, 5; SecurityInfo
0x18000ca15  mov     rcx, rdi; pObjectName
0x18000ca18  call    cs:__imp_GetNamedSecurityInfoW
0x18000ca1e  mov     r12d, eax
0x18000ca21  test    eax, eax
0x18000ca23  jg      loc_18000D02E
0x18000ca29  test    r12d, r12d
0x18000ca2c  js      loc_18000D18F
0x18000ca32  mov     r15, [rsp+530h+ppszServer]
0x18000ca37  mov     [rbp+430h+var_490], r15
0x18000ca3b  mov     r14, [rbp+430h+ppDacl]
0x18000ca3f  mov     [rbp+430h+var_4A8], r14
0x18000ca43  mov     r12d, 8007000Eh
0x18000ca49  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ca50  mov     ecx, 20h ; ' '; unsigned __int64
0x18000ca55  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ca5a  mov     rsi, rax
0x18000ca5d  mov     [rbp+430h+pAce], rax
0x18000ca61  test    rax, rax
0x18000ca64  jz      short loc_18000CACD
0x18000ca66  xor     eax, eax
0x18000ca68  mov     [rsi], rax
0x18000ca6b  mov     [rsi+8], rax
0x18000ca6f  mov     [rsi+10h], rax
0x18000ca73  mov     qword ptr [rsi+18h], 1
0x18000ca7b  test    rsi, rsi
0x18000ca7e  jz      short loc_18000CACD
0x18000ca80  mov     rcx, rsi; this
0x18000ca83  call    ?_Init@CAceList@@AEAAJXZ; CAceList::_Init(void)
0x18000ca88  mov     edi, eax
0x18000ca8a  test    eax, eax
0x18000ca8c  js      loc_18000CE63
0x18000ca92  test    r14, r14
0x18000ca95  jz      loc_18000CE63
0x18000ca9b  xor     eax, eax
0x18000ca9d  mov     [rbp+430h+pAclInformation], rax
0x18000caa1  mov     [rbp+430h+var_470], eax
0x18000caa4  mov     r9d, 2; dwAclInformationClass
0x18000caaa  mov     r8d, 0Ch; nAclInformationLength
0x18000cab0  lea     rdx, [rbp+430h+pAclInformation]; pAclInformation
0x18000cab4  mov     rcx, r14; pAcl
0x18000cab7  call    cs:__imp_GetAclInformation
0x18000cabd  xor     r15d, r15d
0x18000cac0  mov     r13d, r15d
0x18000cac3  mov     dword ptr [rsp+530h+var_4E0], r15d
0x18000cac8  jmp     loc_18000CEC4
0x18000cacd  mov     rcx, [rsp+530h+ppszServer]; hMem
0x18000cad2  call    cs:__imp_LocalFree
0x18000cad8  xor     r15d, r15d
0x18000cadb  test    r12d, r12d
0x18000cade  js      loc_18000D186
0x18000cae4  mov     [rbp+430h+var_4B0], r15
0x18000cae8  mov     dword ptr [rsp+530h+var_4E0], r15d
0x18000caed  mov     rax, [r13+0]
0x18000caf1  lea     r8, [rsp+530h+var_4E0]
0x18000caf6  mov     edx, 60400000h
0x18000cafb  mov     rcx, r13
0x18000cafe  mov     rax, [rax+30h]
0x18000cb02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb07  test    eax, eax
0x18000cb09  js      loc_18000CBE5
0x18000cb0f  cmp     dword ptr [rsp+530h+var_4E0], 60000000h
0x18000cb17  jnz     loc_18000CBE5
0x18000cb1d  mov     esi, 1
0x18000cb22  lea     r8, [rbp+430h+var_4B0]; struct CAceList **
0x18000cb26  mov     edx, esi; int
0x18000cb28  mov     rcx, rbx; struct CAceList *
0x18000cb2b  call    ?_s_GetNonSystemAceList@CFolderAclEngine@@CAJPEAVCAceList@@HPEAPEAV2@@Z; CFolderAclEngine::_s_GetNonSystemAceList(CAceList *,int,CAceList * *)
0x18000cb30  mov     r12d, eax
0x18000cb33  mov     rbx, [rbp+430h+var_4B0]
0x18000cb37  test    eax, eax
0x18000cb39  js      short loc_18000CB88
0x18000cb3b  mov     rcx, rbx; this
0x18000cb3e  call    ?DoesAceListHasMoreThanOneSidForAllow@CAceList@@QEAA_NXZ; CAceList::DoesAceListHasMoreThanOneSidForAllow(void)
0x18000cb43  test    al, al
0x18000cb45  jnz     short loc_18000CB88
0x18000cb47  mov     r14d, r15d
0x18000cb4a  mov     rdi, [rbx+8]
0x18000cb4e  test    rdi, rdi
0x18000cb51  jz      loc_18000D1CB
0x18000cb57  mov     eax, [rdi]
0x18000cb59  cmp     r14d, eax
0x18000cb5c  jl      loc_18000CBED
0x18000cb62  mov     r14d, r15d
0x18000cb65  mov     rdi, [rbx+10h]
0x18000cb69  test    rdi, rdi
0x18000cb6c  jz      loc_18000D1D3
0x18000cb72  mov     eax, [rdi]
0x18000cb74  cmp     r14d, eax
0x18000cb77  jl      loc_18000CC3B
0x18000cb7d  mov     rax, [rsp+530h+var_4C8]
0x18000cb82  mov     dword ptr [rax], 1
0x18000cb88  test    rbx, rbx
0x18000cb8b  jz      short loc_18000CB95
0x18000cb8d  mov     rcx, rbx; this
0x18000cb90  call    ??_GCAceList@@QEAAPEAXI@Z; CAceList::`scalar deleting destructor'(uint)
0x18000cb95  mov     rbx, [rsp+530h+var_4E8]
0x18000cb9a  test    rbx, rbx
0x18000cb9d  jz      short loc_18000CBA8
0x18000cb9f  mov     rcx, rbx; this
0x18000cba2  call    ??_GCAceList@@QEAAPEAXI@Z; CAceList::`scalar deleting destructor'(uint)
0x18000cba7  nop
0x18000cba8  mov     rcx, [rsp+530h+ppwsz]; pv
  ... truncated ...
```
