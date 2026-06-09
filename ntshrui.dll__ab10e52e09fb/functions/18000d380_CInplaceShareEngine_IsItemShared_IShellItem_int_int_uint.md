# CInplaceShareEngine::_IsItemShared(IShellItem *,int,int *,uint *)

- ea: `0x18000d380`
- end: `0x18000dd51`
- name: `?_IsItemShared@CInplaceShareEngine@@AEAAJPEAUIShellItem@@HPEAHPEAI@Z`
- size: `2513`
- prototype: `__int64 __usercall@<rax>(CInplaceShareEngine *__hidden this@<rcx>, struct IShellItem *@<rdx>, int@<r8d>, int *@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001a3b0`

## callees

- `0x180008f68`
- `0x1800098dc`
- `0x18000b240`
- `0x18000bdc0`
- `0x18000d1f0`
- `0x18000d380`
- `0x18000edd0`
- `0x18000f09c`
- `0x18000f0c8`
- `0x18000f250`
- `0x18000f7a0`
- `0x18001cc4c`
- `0x18001d7b4`
- `0x1800254e0`
- `0x1800259bc`
- `0x18005e1c8`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dbe2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dc19`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dbe2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dc19`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000d727`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000d75c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000d847`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000d8a8`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000d727`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000d75c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000d847`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000d8a8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000d6f2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000d80f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000d6f2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000d80f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000d702`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000d81f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000d702`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000d81f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d61b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d929`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000da10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dcbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d61b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d929`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000da10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dcbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db1e`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x18000d55d`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x18000d55d`
- `SHELL32!__imp_SHGetCorrectOwnerSid` at `0x18000dad6`
- `SHELL32!__imp_SHGetCorrectOwnerSid` at `0x18000dad6`
- `SHLWAPI!PathIsRootW` at `0x18000d502`
- `SHLWAPI!PathIsRootW` at `0x18000d54a`
- `SHLWAPI!PathIsRootW` at `0x18000d502`
- `SHLWAPI!PathIsRootW` at `0x18000d54a`
- `netutils!NetApiBufferFree` at `0x18000db9e`
- `netutils!NetApiBufferFree` at `0x18000db9e`
- `srvcli!NetShareEnum` at `0x18000db71`
- `srvcli!NetShareEnum` at `0x18000db71`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000dcac`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000dcac`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000d8f8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000d8f8`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18000d5c0`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18000d5c0`

## pseudocode

```c
__int64 __fastcall CInplaceShareEngine::_IsItemShared(
        CInplaceShareEngine *this,
        struct IShellItem *a2,
        __int64 a3,
        int *a4,
        unsigned int *a5)
{
  int *v5; // rdi
  struct IShellItemVtbl *lpVtbl; // rax
  HRESULT (__stdcall *BindToHandler)(IShellItem *, IBindCtx *, const GUID *const, const IID *const, void **); // rax
  __int64 result; // rax
  int v11; // edi
  bool v12; // sf
  DWORD v13; // r12d
  __int64 v14; // rax
  signed int v15; // r15d
  LPCWSTR v16; // rsi
  signed int NamedSecurityInfoW; // eax
  int v18; // r8d
  PSECURITY_DESCRIPTOR v19; // rdi
  CAceList *v20; // r13
  struct _ACL *v21; // r14
  CAceList *v22; // rbx
  int Error; // edi
  CSharePermissionList *v24; // rax
  CSharePermissionList *v25; // rax
  CSharePermissionList *v26; // r12
  int v27; // esi
  _DWORD *v28; // rbx
  int v29; // eax
  __int64 v30; // rdi
  void *v31; // rbx
  __int64 i; // rbx
  __int64 j; // rbx
  enum SHARE_ROLE RoleForItemAccessMask; // eax
  int v35; // esi
  int *v36; // rbx
  int v37; // eax
  __int64 v38; // rdi
  void *v39; // rbx
  __int64 k; // rbx
  int v41; // eax
  char v42; // al
  __int64 m; // rbx
  enum SHARE_ROLE v44; // eax
  LPWSTR v45; // rcx
  CAceList *v46; // r14
  int v47; // ebx
  int v48; // esi
  DWORD v49; // edi
  __int64 v50; // rax
  unsigned int *v51; // rax
  unsigned int v52; // ecx
  unsigned int v53; // edx
  int v54; // eax
  char v55; // al
  unsigned int v56; // edx
  unsigned int v57; // r9d
  DWORD entriesread[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-B8h] BYREF
  DWORD totalentries[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR pszPath; // [rsp+58h] [rbp-A8h] BYREF
  int *v62; // [rsp+60h] [rbp-A0h]
  CAceList *v63; // [rsp+68h] [rbp-98h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL Sid; // [rsp+78h] [rbp-88h] BYREF
  PACL ppDacl; // [rsp+80h] [rbp-80h] BYREF
  PSID ppsidOwner; // [rsp+88h] [rbp-78h] BYREF
  CInplaceShareEngine *v68; // [rsp+90h] [rbp-70h]
  unsigned int *v69; // [rsp+98h] [rbp-68h]
  unsigned __int16 v70[264]; // [rsp+A0h] [rbp-60h] BYREF

  v62 = a4;
  v5 = a4;
  v68 = this;
  v69 = a5;
  *a4 = 0;
  if ( a5 )
    *a5 = 0;
  lpVtbl = a2->lpVtbl;
  pszPath = 0;
  StringSid = 0;
  BindToHandler = lpVtbl->BindToHandler;
  *(_QWORD *)entriesread = 0;
  if ( ((int (__fastcall *)(struct IShellItem *, _QWORD, const GUID *, GUID *, DWORD *))BindToHandler)(
         a2,
         0,
         &BHID_SFObject,
         &GUID_7d903fca_d6f9_4810_8332_946c0177e247,
         entriesread) < 0 )
    goto LABEL_150;
  *(_QWORD *)totalentries = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, DWORD *))(**(_QWORD **)entriesread + 32LL))(
          *(_QWORD *)entriesread,
          totalentries);
  if ( v11 >= 0 )
  {
    v11 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, LPWSTR *))totalentries)(
            *(_QWORD *)totalentries,
            &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
            &StringSid);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)totalentries + 16LL))(*(_QWORD *)totalentries);
  }
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)entriesread + 16LL))(*(_QWORD *)entriesread);
  v12 = v11 < 0;
  v5 = v62;
  if ( v12 )
  {
LABEL_150:
    result = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, LPWSTR *))a2->lpVtbl->QueryInterface)(
               a2,
               &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
               &StringSid);
    if ( (int)result < 0 )
      return result;
  }
  totalentries[0] = 0;
  v13 = 0;
  v14 = *(_QWORD *)StringSid;
  entriesread[0] = 0;
  v15 = (*(__int64 (__fastcall **)(LPWSTR, __int64, DWORD *))(v14 + 48))(StringSid, 1614807040, totalentries);
  if ( v15 >= 0 )
  {
    v15 = (*(__int64 (__fastcall **)(LPWSTR, __int64, LPCWSTR *))(*(_QWORD *)StringSid + 40LL))(
            StringSid,
            2147844096LL,
            &pszPath);
    if ( v15 >= 0 )
      v13 = totalentries[0];
    entriesread[0] = v13;
  }
  (*(void (__fastcall **)(LPWSTR))(*(_QWORD *)StringSid + 16LL))(StringSid);
  if ( v15 < 0 )
    return (unsigned int)v15;
  if ( PathIsRootW(pszPath) )
    goto LABEL_104;
  if ( v13 == 1610612736 )
    v15 = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR, __int64, int *))(**((_QWORD **)this + 8) + 48LL))(
            *((_QWORD *)this + 8),
            pszPath,
            1,
            v5);
  if ( *v5 || PathIsRootW(pszPath) || PathIsNetworkPathW(pszPath) )
    goto LABEL_104;
  if ( !(unsigned int)CFolderAclEngine::s_DoesVolumeSupportFileSystemAcls(pszPath) )
  {
    *v5 = CInplaceShareEngine::_IsUnderSmbShare(this, pszPath);
    goto LABEL_104;
  }
  v16 = pszPath;
  Sid = 0;
  hMem = 0;
  ppDacl = 0;
  ppsidOwner = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(pszPath, SE_FILE_OBJECT, 5u, &ppsidOwner, 0, &ppDacl, 0, &hMem);
  v15 = NamedSecurityInfoW;
  if ( NamedSecurityInfoW > 0 )
    v15 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
  if ( v15 < 0 )
  {
LABEL_139:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v18, (_DWORD)v16, v15);
    goto LABEL_104;
  }
  v19 = hMem;
  v20 = 0;
  v21 = ppDacl;
  v63 = (CAceList *)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  v22 = v63;
  v15 = -2147024882;
  if ( !v63 )
  {
    Error = -2147024882;
LABEL_26:
    entriesread[0] = v13;
    goto LABEL_27;
  }
  *(_QWORD *)v63 = 0;
  *((_QWORD *)v22 + 1) = 0;
  *((_QWORD *)v22 + 2) = 0;
  *((_QWORD *)v22 + 3) = 1;
  Error = CAceList::_InitFromAclAndSD(v22, v21, v19, 0);
  if ( Error < 0 )
  {
LABEL_115:
    CAceList::`scalar deleting destructor'(v22, v56);
    goto LABEL_26;
  }
  StringSid = 0;
  v20 = v22;
  Error = SHGetCorrectOwnerSid(v16, ppsidOwner, &StringSid);
  if ( Error < 0 )
  {
LABEL_114:
    if ( !v22 )
      goto LABEL_26;
    goto LABEL_115;
  }
  if ( !ConvertStringSidToSidW(StringSid, &Sid) )
  {
    Error = ResultFromKnownLastError();
    LocalFree(StringSid);
    if ( Error >= 0 )
      goto LABEL_26;
    goto LABEL_114;
  }
  Error = 0;
  LocalFree(StringSid);
LABEL_27:
  LocalFree(hMem);
  if ( Error < 0 )
  {
    v15 = Error;
    goto LABEL_139;
  }
  StringSid = (LPWSTR)Sid;
  v63 = 0;
  v24 = (CSharePermissionList *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v24 )
    goto LABEL_102;
  v25 = CSharePermissionList::CSharePermissionList(v24);
  v26 = v25;
  if ( !v25 )
    goto LABEL_89;
  if ( !(unsigned int)CDSA_Base<_SHARE_PERMISSION>::Create((char *)v25 + 16) )
    goto LABEL_88;
  v15 = 0;
  v27 = 0;
  do
  {
    v28 = (_DWORD *)*((_QWORD *)v20 + 1);
    v29 = v28 ? *v28 : 0;
    if ( v27 >= v29 )
      break;
    if ( qword_180095A20 == (__int64 (__fastcall *)(_QWORD, _QWORD))-1LL )
    {
      if ( !g_hinstCC )
      {
        DelayLoadCC();
        if ( !g_hinstCC )
        {
          qword_180095A20 = 0;
LABEL_131:
          v30 = 0;
          goto LABEL_38;
        }
      }
      qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))GetProcAddress(g_hinstCC, (LPCSTR)0x14C);
    }
    if ( !qword_180095A20 )
      goto LABEL_131;
    v30 = qword_180095A20(v28, v27);
LABEL_38:
    if ( (*(_BYTE *)(v30 + 28) & 1) != 0 )
    {
      v31 = *(void **)(v30 + 8);
      if ( !(unsigned int)IsSidLocalMachineAndUnknown(v31) )
      {
        if ( entriesread[0] != 0x20000000
          || (v41 = *(_DWORD *)(v30 + 28), (v41 & 0x20) != 0)
          || (v41 & 1) == 0
          || (v42 = *(_BYTE *)(v30 + 1)) != 0 && v42 != 9 )
        {
          if ( !GetSidSubAuthorityCount(v31) || *GetSidSubAuthority(v31, 0) != 80 )
          {
            for ( i = 0; (unsigned int)i < 0xB; i = (unsigned int)(i + 1) )
            {
              if ( IsWellKnownSid(*(PSID *)(v30 + 8), (WELL_KNOWN_SID_TYPE)dword_180082BA0[i]) )
                goto LABEL_53;
            }
            if ( (*(_BYTE *)(v30 + 28) & 0x20) != 0 )
            {
              for ( j = 0; (unsigned int)j < 2; j = (unsigned int)(j + 1) )
              {
                if ( IsWellKnownSid(*(PSID *)(v30 + 8), (WELL_KNOWN_SID_TYPE)dword_180082B98[j]) )
                  goto LABEL_53;
              }
            }
            RoleForItemAccessMask = GetRoleForItemAccessMask(*(_DWORD *)(v30 + 4));
            v15 = CSharePermissionList::_MergePermission(v26, *(void **)(v30 + 8), RoleForItemAccessMask);
          }
        }
      }
    }
LABEL_53:
    ++v27;
  }
  while ( v15 >= 0 );
  if ( v15 < 0 )
    goto LABEL_88;
  v15 = 0;
  v35 = 0;
  while ( 2 )
  {
    v36 = (int *)*((_QWORD *)v20 + 2);
    if ( v36 )
      v37 = *v36;
    else
      v37 = 0;
    if ( v35 < v37 )
    {
      if ( qword_180095A20 != (__int64 (__fastcall *)(_QWORD, _QWORD))-1LL )
        goto LABEL_60;
      if ( g_hinstCC || (DelayLoadCC(), g_hinstCC) )
      {
        qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))GetProcAddress(g_hinstCC, (LPCSTR)0x14C);
LABEL_60:
        if ( qword_180095A20 )
        {
          v38 = qword_180095A20(v36, v35);
          goto LABEL_62;
        }
      }
      else
      {
        qword_180095A20 = 0;
      }
      v38 = 0;
LABEL_62:
      if ( (*(_BYTE *)(v38 + 28) & 1) != 0 )
      {
        v39 = *(void **)(v38 + 8);
        if ( !(unsigned int)IsSidLocalMachineAndUnknown(v39) )
        {
          if ( entriesread[0] != 0x20000000
            || (v54 = *(_DWORD *)(v38 + 28), (v54 & 0x20) != 0)
            || (v54 & 1) == 0
            || (v55 = *(_BYTE *)(v38 + 1)) != 0 && v55 != 9 )
          {
            if ( !GetSidSubAuthorityCount(v39) || *GetSidSubAuthority(v39, 0) != 80 )
            {
              for ( k = 0; (unsigned int)k < 0xB; k = (unsigned int)(k + 1) )
              {
                if ( IsWellKnownSid(*(PSID *)(v38 + 8), (WELL_KNOWN_SID_TYPE)dword_180082BA0[k]) )
                  goto LABEL_82;
              }
              if ( (*(_BYTE *)(v38 + 28) & 0x20) != 0 )
              {
                for ( m = 0; (unsigned int)m < 2; m = (unsigned int)(m + 1) )
                {
                  if ( IsWellKnownSid(*(PSID *)(v38 + 8), (WELL_KNOWN_SID_TYPE)dword_180082B98[m]) )
                    goto LABEL_82;
                }
              }
              v44 = GetRoleForItemAccessMask(*(_DWORD *)(v38 + 4));
              v15 = CSharePermissionList::_MergePermission(v26, *(void **)(v38 + 8), v44);
            }
          }
        }
      }
LABEL_82:
      ++v35;
      if ( v15 < 0 )
        break;
      continue;
    }
    break;
  }
  if ( v15 >= 0 )
  {
    v45 = StringSid;
    if ( !StringSid
      || ((StringSid = 0, ConvertSidToStringSidW(v45, &StringSid)) || (v15 = ResultFromKnownLastError(), v15 >= 0))
      && (v15 = (*(__int64 (__fastcall **)(CSharePermissionList *, LPWSTR, __int64))(*(_QWORD *)v26 + 56LL))(
                  v26,
                  StringSid,
                  3),
          LocalFree(StringSid),
          v15 >= 0) )
    {
      v15 = (**(__int64 (__fastcall ***)(CSharePermissionList *, GUID *, void **))v26)(
              v26,
              &GUID_4c62a9fa_2437_49ca_8eb4_5238205afeaa,
              (void **)&v63);
    }
  }
LABEL_88:
  (*(void (__fastcall **)(CSharePermissionList *))(*(_QWORD *)v26 + 16LL))(v26);
LABEL_89:
  if ( v15 >= 0 )
  {
    v46 = v63;
    v47 = 0;
    totalentries[0] = 0;
    v48 = (*(__int64 (__fastcall **)(CAceList *, DWORD *))(*(_QWORD *)v63 + 32LL))(v63, totalentries);
    v49 = 0;
    while ( v48 >= 0 )
    {
      if ( v49 >= totalentries[0] )
        goto LABEL_96;
      v50 = *(_QWORD *)v46;
      StringSid = 0;
      entriesread[0] = 0;
      v48 = (*(__int64 (__fastcall **)(CAceList *, _QWORD, LPWSTR *, DWORD *))(v50 + 40))(
              v46,
              v49,
              &StringSid,
              entriesread);
      if ( v48 >= 0 )
      {
        if ( entriesread[0] != 3 )
          v47 = 1;
        CoTaskMemFree(StringSid);
      }
      ++v49;
      if ( v47 )
      {
        if ( v48 < 0 )
          break;
LABEL_96:
        if ( v47 )
        {
          entriesread[0] = 0;
          totalentries[0] = 0;
          StringSid = 0;
          if ( NetShareEnum(0, 2u, (LPBYTE *)&StringSid, 0xFFFFFFFF, entriesread, totalentries, 0) )
          {
            *v62 = 1;
          }
          else
          {
            if ( CInplaceShareEngine::_GetUncPath(v68, pszPath, v70, v57) >= 0 )
              *v62 = 1;
            NetApiBufferFree(StringSid);
          }
        }
        break;
      }
    }
    if ( v69 )
    {
      v51 = (unsigned int *)*((_QWORD *)v20 + 2);
      if ( v51 )
        v52 = *v51;
      else
        v52 = 0;
      *v69 = v52;
    }
    (*(void (__fastcall **)(CAceList *))(*(_QWORD *)v63 + 16LL))(v63);
  }
LABEL_102:
  LocalFree(Sid);
  if ( v20 )
    CAceList::`scalar deleting destructor'(v20, v53);
LABEL_104:
  CoTaskMemFree((LPVOID)pszPath);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000d380  push    rbp
0x18000d382  push    rbx
0x18000d383  push    rsi
0x18000d384  push    rdi
0x18000d385  push    r14
0x18000d387  lea     rbp, [rsp-1D0h]
0x18000d38f  sub     rsp, 2D0h
0x18000d396  mov     rax, cs:__security_cookie
0x18000d39d  xor     rax, rsp
0x18000d3a0  mov     [rbp+1F0h+var_40], rax
0x18000d3a7  mov     rax, [rbp+1F0h+arg_20]
0x18000d3ae  xor     r14d, r14d
0x18000d3b1  mov     [rsp+2F0h+var_290], r9
0x18000d3b6  mov     rdi, r9
0x18000d3b9  mov     [rbp+1F0h+var_260], rcx
0x18000d3bd  mov     rbx, rdx
0x18000d3c0  mov     [rbp+1F0h+var_258], rax
0x18000d3c4  mov     rsi, rcx
0x18000d3c7  mov     [r9], r14d
0x18000d3ca  test    rax, rax
0x18000d3cd  jz      short loc_18000D3D2
0x18000d3cf  mov     [rax], r14d
0x18000d3d2  mov     rax, [rdx]
0x18000d3d5  lea     rcx, [rsp+2F0h+entriesread]
0x18000d3da  mov     [rsp+2F0h+ppsidGroup], rcx
0x18000d3df  lea     r9, _GUID_7d903fca_d6f9_4810_8332_946c0177e247
0x18000d3e6  lea     r8, BHID_SFObject
0x18000d3ed  mov     [rsp+2F0h+pszPath], r14
0x18000d3f2  xor     edx, edx
0x18000d3f4  mov     [rsp+2F0h+StringSid], r14
0x18000d3f9  mov     rax, [rax+18h]
0x18000d3fd  mov     rcx, rbx
0x18000d400  mov     qword ptr [rsp+2F0h+entriesread], r14
0x18000d405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d40a  test    eax, eax
0x18000d40c  jns     short loc_18000D432
0x18000d40e  mov     rax, [rbx]
0x18000d411  lea     r8, [rsp+2F0h+StringSid]
0x18000d416  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18000d41d  mov     rcx, rbx
0x18000d420  mov     rax, [rax]
0x18000d423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d428  test    eax, eax
0x18000d42a  js      loc_18000DA49
0x18000d430  jmp     short loc_18000D471
0x18000d432  mov     rcx, qword ptr [rsp+2F0h+entriesread]
0x18000d437  lea     rdx, [rsp+2F0h+totalentries]
0x18000d43c  mov     qword ptr [rsp+2F0h+totalentries], r14
0x18000d441  mov     rax, [rcx]
0x18000d444  mov     rax, [rax+20h]
0x18000d448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d44d  mov     edi, eax
0x18000d44f  test    eax, eax
0x18000d451  jns     loc_18000DC4F
0x18000d457  mov     rcx, qword ptr [rsp+2F0h+entriesread]
0x18000d45c  mov     rax, [rcx]
0x18000d45f  mov     rax, [rax+10h]
0x18000d463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d468  test    edi, edi
0x18000d46a  mov     rdi, [rsp+2F0h+var_290]
0x18000d46f  js      short loc_18000D40E
0x18000d471  mov     rcx, [rsp+2F0h+StringSid]
0x18000d476  lea     r8, [rsp+2F0h+totalentries]
0x18000d47b  mov     [rsp+2F0h+totalentries], r14d
0x18000d480  mov     edx, 60400000h
0x18000d485  mov     [rsp+2F0h+arg_10], r12
0x18000d48d  mov     r12d, r14d
0x18000d490  mov     [rsp+2F0h+var_30], r15
0x18000d498  mov     rax, [rcx]
0x18000d49b  mov     [rsp+2F0h+entriesread], r14d
0x18000d4a0  mov     rax, [rax+30h]
0x18000d4a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4a9  mov     r15d, eax
0x18000d4ac  test    eax, eax
0x18000d4ae  js      short loc_18000D4DB
0x18000d4b0  mov     rcx, [rsp+2F0h+StringSid]
0x18000d4b5  lea     r8, [rsp+2F0h+pszPath]
0x18000d4ba  mov     edx, 80058000h
0x18000d4bf  mov     rax, [rcx]
0x18000d4c2  mov     rax, [rax+28h]
0x18000d4c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4cb  test    eax, eax
0x18000d4cd  mov     r15d, eax
0x18000d4d0  cmovns  r12d, [rsp+2F0h+totalentries]
0x18000d4d6  mov     [rsp+2F0h+entriesread], r12d
0x18000d4db  mov     rcx, [rsp+2F0h+StringSid]
0x18000d4e0  mov     rax, [rcx]
0x18000d4e3  mov     rax, [rax+10h]
0x18000d4e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4ec  test    r15d, r15d
0x18000d4ef  js      loc_18000DA36
0x18000d4f5  mov     rcx, [rsp+2F0h+pszPath]; pszPath
0x18000d4fa  mov     [rsp+2F0h+var_28], r13
0x18000d502  call    cs:__imp_PathIsRootW
0x18000d508  test    eax, eax
0x18000d50a  jnz     loc_18000DA23
0x18000d510  mov     ebx, 1
0x18000d515  cmp     r12d, 60000000h
0x18000d51c  jnz     short loc_18000D53C
0x18000d51e  mov     rcx, [rsi+40h]
0x18000d522  mov     r9, rdi
0x18000d525  mov     rdx, [rsp+2F0h+pszPath]
0x18000d52a  mov     r8d, ebx
0x18000d52d  mov     rax, [rcx]
0x18000d530  mov     rax, [rax+30h]
0x18000d534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d539  mov     r15d, eax
0x18000d53c  cmp     [rdi], r14d
0x18000d53f  jnz     loc_18000DA23
0x18000d545  mov     rcx, [rsp+2F0h+pszPath]; pszPath
0x18000d54a  call    cs:__imp_PathIsRootW
0x18000d550  test    eax, eax
0x18000d552  jnz     loc_18000DA23
0x18000d558  mov     rcx, [rsp+2F0h+pszPath]; pszPath
0x18000d55d  call    cs:__imp_PathIsNetworkPathW
0x18000d563  test    eax, eax
0x18000d565  jnz     loc_18000DA23
0x18000d56b  mov     rcx, [rsp+2F0h+pszPath]; unsigned __int16 *
0x18000d570  call    ?s_DoesVolumeSupportFileSystemAcls@CFolderAclEngine@@SAHPEBG@Z; CFolderAclEngine::s_DoesVolumeSupportFileSystemAcls(ushort const *)
0x18000d575  test    eax, eax
0x18000d577  jz      loc_18000DBA9
0x18000d57d  mov     rsi, [rsp+2F0h+pszPath]
0x18000d582  lea     rax, [rsp+2F0h+hMem]
0x18000d587  mov     [rsp+2F0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18000d58c  lea     r9, [rbp+1F0h+ppsidOwner]; ppsidOwner
0x18000d590  lea     rax, [rbp+1F0h+var_270]
0x18000d594  mov     [rsp+2F0h+ppSacl], r14; ppSacl
0x18000d599  mov     [rsp+2F0h+ppDacl], rax; ppDacl
0x18000d59e  mov     r8d, 5; SecurityInfo
0x18000d5a4  mov     edx, ebx; ObjectType
0x18000d5a6  mov     [rsp+2F0h+ppsidGroup], r14; ppsidGroup
0x18000d5ab  mov     rcx, rsi; pObjectName
0x18000d5ae  mov     [rsp+2F0h+Sid], r14
0x18000d5b3  mov     [rsp+2F0h+hMem], r14
0x18000d5b8  mov     [rbp+1F0h+var_270], r14
0x18000d5bc  mov     [rbp+1F0h+ppsidOwner], r14
0x18000d5c0  call    cs:__imp_GetNamedSecurityInfoW
0x18000d5c6  mov     r15d, eax
0x18000d5c9  test    eax, eax
0x18000d5cb  jg      loc_18000DAFC
0x18000d5d1  test    r15d, r15d
0x18000d5d4  js      loc_18000DCCB
0x18000d5da  mov     rdi, [rsp+2F0h+hMem]
0x18000d5df  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d5e6  mov     r13, r14
0x18000d5e9  mov     ecx, 20h ; ' '; unsigned __int64
0x18000d5ee  mov     r14, [rbp+1F0h+var_270]
0x18000d5f2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d5f7  mov     [rsp+2F0h+var_288], rax
0x18000d5fc  mov     rbx, rax
0x18000d5ff  mov     r15d, 8007000Eh
0x18000d605  test    rax, rax
0x18000d608  jnz     loc_18000DA92
0x18000d60e  mov     edi, r15d
0x18000d611  mov     [rsp+2F0h+entriesread], r12d
0x18000d616  mov     rcx, [rsp+2F0h+hMem]; hMem
0x18000d61b  call    cs:__imp_LocalFree
0x18000d621  test    edi, edi
0x18000d623  js      loc_18000DCC8
0x18000d629  mov     rax, [rsp+2F0h+Sid]
0x18000d62e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d635  mov     ecx, 18h; unsigned __int64
0x18000d63a  mov     [rsp+2F0h+StringSid], rax
0x18000d63f  mov     [rsp+2F0h+var_288], 0
0x18000d648  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d64d  test    rax, rax
0x18000d650  jz      loc_18000DA0B
0x18000d656  mov     rcx, rax; this
0x18000d659  call    ??0CSharePermissionList@@QEAA@XZ; CSharePermissionList::CSharePermissionList(void)
0x18000d65e  mov     r12, rax
0x18000d661  test    rax, rax
0x18000d664  jz      loc_18000D962
0x18000d66a  lea     rcx, [rax+10h]
0x18000d66e  call    ?Create@?$CDSA_Base@U_SHARE_PERMISSION@@@@QEAAHH@Z; CDSA_Base<_SHARE_PERMISSION>::Create(int)
0x18000d673  test    eax, eax
0x18000d675  jz      loc_18000D952
0x18000d67b  xor     r15d, r15d
0x18000d67e  xor     esi, esi
0x18000d680  mov     rbx, [r13+8]
0x18000d684  test    rbx, rbx
0x18000d687  jz      loc_18000DD07
0x18000d68d  mov     eax, [rbx]
0x18000d68f  cmp     esi, eax
0x18000d691  jge     loc_18000D78F
0x18000d697  cmp     cs:qword_180095A20, 0FFFFFFFFFFFFFFFFh
0x18000d69f  jz      loc_18000DBBD
0x18000d6a5  mov     rax, cs:qword_180095A20
0x18000d6ac  test    rax, rax
0x18000d6af  jz      loc_18000DC36
0x18000d6b5  movsxd  rdx, esi
0x18000d6b8  mov     rcx, rbx
0x18000d6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6c0  mov     rdi, rax
0x18000d6c3  test    byte ptr [rdi+1Ch], 1
0x18000d6c7  jz      loc_18000D784
0x18000d6cd  mov     rbx, [rdi+8]
0x18000d6d1  mov     rcx, rbx; Sid
0x18000d6d4  call    ?IsSidLocalMachineAndUnknown@@YAHPEAX@Z; IsSidLocalMachineAndUnknown(void *)
0x18000d6d9  test    eax, eax
0x18000d6db  jnz     loc_18000D784
0x18000d6e1  cmp     [rsp+2F0h+entriesread], 20000000h
0x18000d6e9  jz      loc_18000D855
0x18000d6ef  mov     rcx, rbx; pSid
0x18000d6f2  call    cs:__imp_GetSidSubAuthorityCount
0x18000d6f8  test    rax, rax
0x18000d6fb  jz      short loc_18000D70D
0x18000d6fd  xor     edx, edx; nSubAuthority
0x18000d6ff  mov     rcx, rbx; pSid
0x18000d702  call    cs:__imp_GetSidSubAuthority
0x18000d708  cmp     dword ptr [rax], 50h ; 'P'
0x18000d70b  jz      short loc_18000D784
0x18000d70d  xor     ebx, ebx
0x18000d70f  nop
0x18000d710  cmp     ebx, 0Bh
0x18000d713  jnb     short loc_18000D735
0x18000d715  mov     rcx, [rdi+8]; pSid
0x18000d719  lea     rax, __ImageBase
0x18000d720  mov     edx, ds:rva dword_180082BA0[rax+rbx*4]; WellKnownSidType
0x18000d727  call    cs:__imp_IsWellKnownSid
0x18000d72d  test    eax, eax
0x18000d72f  jnz     short loc_18000D784
0x18000d731  inc     ebx
0x18000d733  jmp     short loc_18000D710
0x18000d735  test    byte ptr [rdi+1Ch], 20h
0x18000d739  mov     eax, [rsp+2F0h+entriesread]
0x18000d73d  mov     [rsp+2F0h+entriesread], eax
0x18000d741  jz      short loc_18000D76A
0x18000d743  xor     ebx, ebx
0x18000d745  cmp     ebx, 2
0x18000d748  jnb     short loc_18000D76A
0x18000d74a  mov     rcx, [rdi+8]; pSid
0x18000d74e  lea     rax, __ImageBase
0x18000d755  mov     edx, ds:rva dword_180082B98[rax+rbx*4]; WellKnownSidType
0x18000d75c  call    cs:__imp_IsWellKnownSid
0x18000d762  test    eax, eax
0x18000d764  jnz     short loc_18000D784
0x18000d766  inc     ebx
0x18000d768  jmp     short loc_18000D745
0x18000d76a  mov     ecx, [rdi+4]; unsigned int
0x18000d76d  call    ?GetRoleForItemAccessMask@@YA?AW4SHARE_ROLE@@K@Z; GetRoleForItemAccessMask(ulong)
0x18000d772  mov     rdx, [rdi+8]; void *
0x18000d776  mov     r8d, eax; enum SHARE_ROLE
0x18000d779  mov     rcx, r12; this
0x18000d77c  call    ?_MergePermission@CSharePermissionList@@AEAAJPEAXW4SHARE_ROLE@@@Z; CSharePermissionList::_MergePermission(void *,SHARE_ROLE)
0x18000d781  mov     r15d, eax
0x18000d784  inc     esi
0x18000d786  test    r15d, r15d
0x18000d789  jns     loc_18000D680
0x18000d78f  test    r15d, r15d
0x18000d792  js      loc_18000D952
0x18000d798  xor     r15d, r15d
0x18000d79b  xor     esi, esi
0x18000d79d  mov     rbx, [r13+10h]
0x18000d7a1  test    rbx, rbx
0x18000d7a4  jz      loc_18000DD0E
0x18000d7aa  mov     eax, [rbx]
0x18000d7ac  cmp     esi, eax
0x18000d7ae  jge     loc_18000D8DB
0x18000d7b4  cmp     cs:qword_180095A20, 0FFFFFFFFFFFFFFFFh
0x18000d7bc  jz      loc_18000DBF4
0x18000d7c2  mov     rax, cs:qword_180095A20
0x18000d7c9  test    rax, rax
0x18000d7cc  jz      loc_18000DC48
0x18000d7d2  movsxd  rdx, esi
0x18000d7d5  mov     rcx, rbx
0x18000d7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7dd  mov     rdi, rax
0x18000d7e0  test    byte ptr [rdi+1Ch], 1
0x18000d7e4  jz      loc_18000D8D0
0x18000d7ea  mov     rbx, [rdi+8]
0x18000d7ee  mov     rcx, rbx; Sid
0x18000d7f1  call    ?IsSidLocalMachineAndUnknown@@YAHPEAX@Z; IsSidLocalMachineAndUnknown(void *)
0x18000d7f6  test    eax, eax
0x18000d7f8  jnz     loc_18000D8D0
0x18000d7fe  cmp     [rsp+2F0h+entriesread], 20000000h
0x18000d806  jz      loc_18000DA66
0x18000d80c  mov     rcx, rbx; pSid
0x18000d80f  call    cs:__imp_GetSidSubAuthorityCount
0x18000d815  test    rax, rax
0x18000d818  jz      short loc_18000D82E
0x18000d81a  xor     edx, edx; nSubAuthority
0x18000d81c  mov     rcx, rbx; pSid
0x18000d81f  call    cs:__imp_GetSidSubAuthority
0x18000d825  cmp     dword ptr [rax], 50h ; 'P'
0x18000d828  jz      loc_18000D8D0
0x18000d82e  xor     ebx, ebx
0x18000d830  cmp     ebx, 0Bh
0x18000d833  jnb     short loc_18000D881
0x18000d835  mov     rcx, [rdi+8]; pSid
0x18000d839  lea     rax, __ImageBase
0x18000d840  mov     edx, ds:rva dword_180082BA0[rax+rbx*4]; WellKnownSidType
0x18000d847  call    cs:__imp_IsWellKnownSid
0x18000d84d  test    eax, eax
0x18000d84f  jnz     short loc_18000D8D0
0x18000d851  inc     ebx
0x18000d853  jmp     short loc_18000D830
0x18000d855  mov     eax, [rdi+1Ch]
0x18000d858  test    al, 20h
0x18000d85a  jnz     loc_18000D6EF
0x18000d860  test    al, 1
  ... truncated ...
```
