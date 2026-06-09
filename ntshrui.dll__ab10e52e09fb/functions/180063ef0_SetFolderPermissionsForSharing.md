# SetFolderPermissionsForSharing

- ea: `0x180063ef0`
- end: `0x180064590`
- name: `SetFolderPermissionsForSharing`
- size: `1696`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int, HWND)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180009340`
- `0x180011ba0`
- `0x180011cb0`
- `0x180011df0`
- `0x1800254e0`
- `0x18002637c`
- `0x18002ad40`
- `0x18005e334`
- `0x18005e42c`
- `0x1800638a4`
- `0x180063af0`
- `0x180063bec`
- `0x180063ef0`
- `0x1800726c4`
- `0x180072ae4`
- `0x180072f1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800640ba`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800640ba`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800640dd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800640dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180064560`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180064560`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064569`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064569`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180064419`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180064419`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800641c0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180064453`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800641c0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180064453`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180064318`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180064318`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x1800641eb`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x1800641eb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800643b1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800643b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064181`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800641fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064271`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064548`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064553`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064573`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064181`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800641fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064271`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064548`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064553`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064573`
- `SHELL32!SHChangeNotify` at `0x1800644fb`
- `SHELL32!SHChangeNotify` at `0x1800644fb`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180063fce`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180063fce`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x18006424d`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x18006424d`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180064122`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180064122`
- `ADVAPI32!TreeResetNamedSecurityInfoW` at `0x1800644b2`
- `ADVAPI32!TreeResetNamedSecurityInfoW` at `0x1800644b2`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180064537`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180064537`
- `ADVAPI32!GetEffectiveRightsFromAclW` at `0x180064266`
- `ADVAPI32!GetEffectiveRightsFromAclW` at `0x180064266`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SetFolderPermissionsForSharing(unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3, HWND a4)
{
  unsigned __int16 *v6; // r14
  unsigned int v8; // eax
  int v9; // r13d
  CShareCache *v10; // rcx
  struct CShareInfo *v12; // rdi
  int v13; // eax
  CShareInfo *i; // rcx
  CShareInfo *v15; // rsi
  unsigned __int16 *Netname; // rax
  unsigned int v17; // edx
  WCHAR v18; // dx
  __int64 v19; // r9
  unsigned __int16 *v20; // r8
  int v21; // eax
  HANDLE v22; // rax
  void *v23; // rbx
  WORD v24; // r13
  const wchar_t *v25; // rbx
  const wchar_t *v26; // rcx
  PACL v27; // rbx
  bool v28; // zf
  int v29; // r8d
  const wchar_t *v30; // rcx
  int v31; // edx
  unsigned int v32; // r9d
  DWORD v33; // ecx
  PACL v34; // r14
  BOOL v35; // eax
  __int64 v36; // rcx
  int v37; // eax
  unsigned int v38; // ebx
  struct _ACL *v39; // rcx
  struct _ACL *v40; // rax
  struct _ACL *v41; // r14
  SECURITY_INFORMATION v42; // r8d
  CShareInfo *v43; // rbx
  struct CShareInfo *v44; // r14
  unsigned __int16 *Path; // rax
  _QWORD *v46; // rdx
  WORD pControl[2]; // [rsp+60h] [rbp-A0h] BYREF
  PACL pDacl; // [rsp+68h] [rbp-98h] BYREF
  DWORD pAccessRights; // [rsp+70h] [rbp-90h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+78h] [rbp-88h] BYREF
  int v51; // [rsp+80h] [rbp-80h]
  DWORD dwRevision[2]; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v53; // [rsp+90h] [rbp-70h]
  struct CShareInfo *v54; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL v55; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL v56; // [rsp+A8h] [rbp-58h]
  HANDLE v57; // [rsp+B0h] [rbp-50h]
  struct _TRUSTEE_W pTrustee; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR Name; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v60; // [rsp+DAh] [rbp-26h]
  __int128 v61; // [rsp+EAh] [rbp-16h]
  _BYTE v62[26]; // [rsp+FAh] [rbp-6h] BYREF

  pAccessRights = 0;
  *(_QWORD *)dwRevision = 0;
  v6 = a2;
  v55 = 0;
  if ( a3 > 3 )
    return 0;
  v8 = _CheckFolderType(a1, a2, (int *)&pAccessRights, (const unsigned __int16 **)dwRevision);
  v51 = v8;
  if ( (v8 & 9) == 0 )
    return 0;
  v9 = v8 & 2;
  if ( (v8 & 2) == 0 && !a3 )
    return 0;
  if ( !(unsigned int)DoesVolumeSupportSecurity(a1) )
    return a3 != 0;
  v54 = 0;
  v12 = 0;
  if ( !a3 )
  {
    v13 = CShareCache::ConstructParentWarnList(v10, a1, &v54);
    v12 = v54;
    if ( v13 >= 0 && v54 && a4 )
    {
      if ( ShellMessageBoxW(g_hInstance, a4, (LPCWSTR)0x76, (LPCWSTR)0xC80, 0x34u) == 7 )
      {
LABEL_12:
        DeleteShareInfoList(v12, 1);
        return 0;
      }
      for ( i = *(CShareInfo **)v12; i != v12; i = v15 )
      {
        v15 = *(CShareInfo **)i;
        Netname = CShareInfo::GetNetname(i);
        if ( ConfirmStopShare(a4, v17, Netname) != 6 )
          goto LABEL_12;
      }
    }
  }
  v53 = 0;
  if ( !v6 || !*v6 )
  {
    GetCurrentUserStringSid((LPWSTR *)&v55);
    v6 = (unsigned __int16 *)v55;
  }
  v18 = *a1;
  Name = 0;
  v19 = 314159269;
  memset(v62, 0, sizeof(v62));
  v60 = 0;
  v61 = 0;
  if ( v18 )
  {
    v20 = a1;
    do
    {
      ++v20;
      v21 = v18;
      v18 = *v20;
      v19 = (v21 + ((unsigned int)v19 >> 2) + 2080 * (_DWORD)v19) ^ (unsigned int)v19;
    }
    while ( *v20 );
  }
  LODWORD(v19) = v19 & 0x7FFFFFFF;
  StringCchPrintfW(&Name, 0x1Eu, L"share perms %x", v19);
  v22 = CreateMutexW(0, 0, &Name);
  v57 = v22;
  v23 = v22;
  if ( v22 )
  {
    WaitForSingleObject(v22, 0x7530u);
    if ( !v6 || (hMem = 0, pDacl = 0, GetNamedSecurityInfoW(a1, SE_FILE_OBJECT, 4u, 0, 0, &pDacl, 0, &hMem)) )
    {
LABEL_83:
      ReleaseMutex(v23);
      CloseHandle(v23);
      goto LABEL_84;
    }
    v56 = 0;
    if ( !v9 )
    {
      v24 = 0;
      goto LABEL_41;
    }
    v24 = 0;
    if ( (unsigned int)_IsDaclPrivateForUser(pDacl, v6) )
    {
      if ( !a3 )
      {
        v53 = 1;
LABEL_36:
        v27 = 0;
        pDacl = 0;
LABEL_42:
        v28 = (v51 & 8) == 0;
        v29 = v51 & 8;
        v51 = v29;
        if ( !v28 )
        {
          if ( !v27 )
            goto LABEL_82;
          pAccessRights = 0;
          memset(&pTrustee, 0, sizeof(pTrustee));
          BuildTrusteeWithSidW(&pTrustee, qword_180082178);
          pTrustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
          GetEffectiveRightsFromAclW(v27, &pTrustee, &pAccessRights);
          LocalFree(hMem);
          v30 = L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OICIIO;GA;;;CO)(A;CIOI;GRGX;;;BU)(A;CI;4;;;BU)(A;CIIO;2;;;BU)(A;;GRGX;;;WD)";
          hMem = 0;
          if ( (pAccessRights & 0xC0000) != 0 )
            v30 = L"D:P(A;OICI;GA;;;WD)";
          pDacl = 0;
          _MakeSecurityDescriptorForUser(v30, v6, &hMem, &pDacl);
          v29 = v51;
          v27 = pDacl;
        }
        if ( v27 )
        {
          if ( !a3 )
            goto LABEL_71;
          v31 = 0;
          v32 = a3 - 1;
          v33 = 0;
          *(_DWORD *)pControl = a3 - 1;
          pAccessRights = 0;
          v34 = v27 + 1;
          if ( !v27->AceCount )
            goto LABEL_61;
          while ( 1 )
          {
            if ( (v34->Sbz1 & 0x10) != 0 )
            {
              v32 = *(_DWORD *)pControl;
LABEL_60:
              v12 = v54;
LABEL_61:
              v27->AceCount = v24;
              if ( !v32 )
                goto LABEL_70;
              v38 = v33 + 28;
              v39 = pDacl;
              if ( v38 > pDacl->AclSize )
              {
                v40 = (struct _ACL *)LocalAlloc(0x40u, v38);
                v56 = v40;
                v41 = v40;
                if ( v40 )
                {
                  memcpy_0(v40, pDacl, pDacl->AclSize);
                  v39 = v41;
                  v41->AclSize = v38;
                }
                else
                {
                  v39 = 0;
                }
                v32 = *(_DWORD *)pControl;
                pDacl = v39;
              }
              if ( v39 )
              {
                if ( !AddAccessAllowedAceEx(
                        v39,
                        2u,
                        qword_180082160[v32],
                        HIDWORD(qword_180082160[v32]),
                        qword_180082178) )
                {
                  v27 = 0;
                  pDacl = 0;
                  goto LABEL_71;
                }
LABEL_70:
                v27 = pDacl;
LABEL_71:
                if ( v27 )
                {
                  pControl[0] = 0;
                  dwRevision[0] = 0;
                  GetSecurityDescriptorControl(hMem, pControl, dwRevision);
                  v42 = (pControl[0] & 0x1000) != 0 ? -2147483644 : 536870916;
                  if ( a3 )
                  {
                    if ( !SetNamedSecurityInfoW(a1, SE_FILE_OBJECT, v42, 0, 0, pDacl, 0) )
                      goto LABEL_81;
                  }
                  else if ( !TreeResetNamedSecurityInfoW(
                               a1,
                               SE_FILE_OBJECT,
                               v42,
                               0,
                               0,
                               pDacl,
                               0,
                               0,
                               0,
                               ProgressInvokeNever,
                               0) )
                  {
                    if ( v12 )
                    {
                      v43 = *(CShareInfo **)v12;
                      if ( *(struct CShareInfo **)v12 != v12 )
                      {
                        do
                        {
                          v44 = *(struct CShareInfo **)v43;
                          if ( *((_DWORD *)v43 + 5) != 1 )
                          {
                            *((_DWORD *)v43 + 5) = 2;
                            CShareInfo::Commit(v43);
                            Path = CShareInfo::GetPath(v43);
                            SHChangeNotify(512, 5u, Path, 0);
                          }
                          *(_QWORD *)(*(_QWORD *)v43 + 8LL) = *((_QWORD *)v43 + 1);
                          v46 = (_QWORD *)*((_QWORD *)v43 + 1);
                          *v46 = *(_QWORD *)v43;
                          CShareInfo::`scalar deleting destructor'(v43, (unsigned int)v46);
                          v43 = v44;
                        }
                        while ( v44 != v12 );
                      }
                    }
LABEL_81:
                    v53 = 1;
                  }
                }
              }
              goto LABEL_82;
            }
            ++v24;
            v33 += v34->AclSize;
            dwRevision[0] = v33;
            if ( v29 || v34->AclRevision > 3u )
              goto LABEL_56;
            v35 = EqualSid(&v34[1], qword_180082178);
            v31 = pAccessRights;
            v29 = v51;
            if ( !v35 )
              break;
            v36 = *(unsigned int *)pControl;
            v32 = 0;
            *(_DWORD *)pControl = 0;
            v34->Sbz1 = qword_180082160[v36];
            v37 = HIDWORD(qword_180082160[v36]);
            v33 = dwRevision[0];
            *(_DWORD *)&v34->AceCount = v37;
            v27 = pDacl;
LABEL_57:
            ++v31;
            v34 = (PACL)((char *)v34 + v34->AclSize);
            pAccessRights = v31;
            if ( v31 >= v27->AceCount )
              goto LABEL_60;
          }
          v27 = pDacl;
          v33 = dwRevision[0];
LABEL_56:
          v32 = *(_DWORD *)pControl;
          goto LABEL_57;
        }
LABEL_82:
        LocalFree(v56);
        LocalFree(hMem);
        v23 = v57;
        goto LABEL_83;
      }
      if ( pAccessRights )
      {
        v25 = *(const wchar_t **)dwRevision;
        if ( *(_QWORD *)dwRevision )
        {
          LocalFree(hMem);
          v26 = v25;
LABEL_34:
          pDacl = 0;
          hMem = 0;
          _MakeSecurityDescriptorForUser(v26, v6, &hMem, &pDacl);
        }
      }
      else
      {
        pControl[0] = 0;
        dwRevision[0] = 0;
        GetSecurityDescriptorControl(hMem, pControl, dwRevision);
        if ( (pControl[0] & 0x1000) == 0 )
          goto LABEL_36;
        pDacl->AceCount = 0;
        SetSecurityDescriptorControl(hMem, 0x1000u, 0);
      }
LABEL_41:
      v27 = pDacl;
      goto LABEL_42;
    }
    if ( a3 )
      goto LABEL_41;
    LocalFree(hMem);
    v26 = L"D:P(A;OICI;GA;;;SY)(A;OICI;GA;;;%1)";
    goto LABEL_34;
  }
LABEL_84:
  LocalFree(v55);
  if ( v12 )
    DeleteShareInfoList(v12, 1);
  return v53;
}

```

## disassembly

```asm
0x180063ef0  push    rbp
0x180063ef2  push    rbx
0x180063ef3  push    rsi
0x180063ef4  push    rdi
0x180063ef5  push    r12
0x180063ef7  push    r13
0x180063ef9  push    r14
0x180063efb  push    r15
0x180063efd  lea     rbp, [rsp-28h]
0x180063f02  sub     rsp, 128h
0x180063f09  mov     rax, cs:__security_cookie
0x180063f10  xor     rax, rsp
0x180063f13  mov     [rbp+60h+var_48], rax
0x180063f17  xor     esi, esi
0x180063f19  mov     rbx, r9
0x180063f1c  mov     [rsp+160h+pAccessRights], esi
0x180063f20  mov     r15d, r8d
0x180063f23  mov     qword ptr [rbp+60h+dwRevision], rsi
0x180063f27  mov     r14, rdx
0x180063f2a  mov     [rbp+60h+var_C0], rsi
0x180063f2e  mov     r12, rcx
0x180063f31  cmp     r8d, 3
0x180063f35  ja      loc_180063FE6
0x180063f3b  lea     r9, [rbp+60h+dwRevision]; unsigned __int16 **
0x180063f3f  lea     r8, [rsp+160h+pAccessRights]; int *
0x180063f44  call    ?_CheckFolderType@@YAKPEBG0PEAHPEAPEBG@Z; _CheckFolderType(ushort const *,ushort const *,int *,ushort const * *)
0x180063f49  mov     [rbp+60h+var_E0], eax
0x180063f4c  test    al, 9
0x180063f4e  jz      loc_180063FE6
0x180063f54  mov     r13d, eax
0x180063f57  and     r13d, 2
0x180063f5b  jnz     short loc_180063F66
0x180063f5d  test    r15d, r15d
0x180063f60  jz      loc_180063FE6
0x180063f66  mov     rcx, r12; lpszFileName
0x180063f69  call    ?DoesVolumeSupportSecurity@@YAHPEBG@Z; DoesVolumeSupportSecurity(ushort const *)
0x180063f6e  test    eax, eax
0x180063f70  jnz     short loc_180063F7C
0x180063f72  test    r15d, r15d
0x180063f75  mov     eax, esi
0x180063f77  setnz   al
0x180063f7a  jmp     short loc_180063FE8
0x180063f7c  mov     [rbp+60h+var_C8], rsi
0x180063f80  mov     rdi, rsi
0x180063f83  test    r15d, r15d
0x180063f86  jnz     loc_18006402F
0x180063f8c  lea     r8, [rbp+60h+var_C8]; struct CShareInfo **
0x180063f90  mov     rdx, r12; unsigned __int16 *
0x180063f93  call    ?ConstructParentWarnList@CShareCache@@QEAAJPEBGPEAPEAVCShareInfo@@@Z; CShareCache::ConstructParentWarnList(ushort const *,CShareInfo * *)
0x180063f98  mov     rdi, [rbp+60h+var_C8]
0x180063f9c  test    eax, eax
0x180063f9e  js      loc_18006402F
0x180063fa4  test    rdi, rdi
0x180063fa7  jz      loc_18006402F
0x180063fad  test    rbx, rbx
0x180063fb0  jz      short loc_18006402F
0x180063fb2  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hAppInst
0x180063fb9  lea     r8d, [r15+76h]; lpcText
0x180063fbd  mov     r9d, 0C80h; lpcTitle
0x180063fc3  mov     [rsp+160h+fuStyle], 34h ; '4'; fuStyle
0x180063fcb  mov     rdx, rbx; hWnd
0x180063fce  call    cs:__imp_ShellMessageBoxW
0x180063fd4  cmp     eax, 7
0x180063fd7  jnz     short loc_180064008
0x180063fd9  mov     edx, 1; int
0x180063fde  mov     rcx, rdi; struct CShareInfo *
0x180063fe1  call    ?DeleteShareInfoList@@YAXPEAVCShareInfo@@H@Z; DeleteShareInfoList(CShareInfo *,int)
0x180063fe6  xor     eax, eax
0x180063fe8  mov     rcx, [rbp+60h+var_48]
0x180063fec  xor     rcx, rsp; StackCookie
0x180063fef  call    __security_check_cookie
0x180063ff4  add     rsp, 128h
0x180063ffb  pop     r15
0x180063ffd  pop     r14
0x180063fff  pop     r13
0x180064001  pop     r12
0x180064003  pop     rdi
0x180064004  pop     rsi
0x180064005  pop     rbx
0x180064006  pop     rbp
0x180064007  retn
0x180064008  mov     rcx, [rdi]; this
0x18006400b  cmp     rcx, rdi
0x18006400e  jz      short loc_18006402D
0x180064010  mov     rsi, [rcx]
0x180064013  call    ?GetNetname@CShareInfo@@QEAAPEAGXZ; CShareInfo::GetNetname(void)
0x180064018  mov     r8, rax; unsigned __int16 *
0x18006401b  mov     rcx, rbx; HWND
0x18006401e  call    ?ConfirmStopShare@@YAKPEAUHWND__@@IPEAG@Z; ConfirmStopShare(HWND__ *,uint,ushort *)
0x180064023  cmp     eax, 6
0x180064026  jnz     short loc_180063FD9
0x180064028  mov     rcx, rsi
0x18006402b  jmp     short loc_18006400B
0x18006402d  xor     esi, esi
0x18006402f  mov     [rbp+60h+var_D0], esi
0x180064032  test    r14, r14
0x180064035  jz      short loc_18006403D
0x180064037  cmp     si, [r14]
0x18006403b  jnz     short loc_18006404A
0x18006403d  lea     rcx, [rbp+60h+var_C0]; StringSid
0x180064041  call    ?GetCurrentUserStringSid@@YAJPEAPEAG@Z; GetCurrentUserStringSid(ushort * *)
0x180064046  mov     r14, [rbp+60h+var_C0]
0x18006404a  movzx   edx, word ptr [r12]
0x18006404f  xorps   xmm0, xmm0
0x180064052  mov     [rbp+60h+Name], si
0x180064056  mov     r9d, 12B9B0A5h
0x18006405c  movups  xmmword ptr [rbp+60h+var_66], xmm0
0x180064060  movups  xmmword ptr [rbp+60h+var_66+0Ah], xmm0
0x180064064  movups  [rbp+60h+var_86], xmm0
0x180064068  movups  [rbp+60h+var_76], xmm0
0x18006406c  test    dx, dx
0x18006406f  jz      short loc_180064098
0x180064071  mov     r8, r12
0x180064074  imul    ecx, r9d, 820h
0x18006407b  lea     r8, [r8+2]
0x18006407f  mov     eax, r9d
0x180064082  shr     eax, 2
0x180064085  add     ecx, eax
0x180064087  movzx   eax, dx
0x18006408a  movzx   edx, word ptr [r8]
0x18006408e  add     ecx, eax
0x180064090  xor     r9d, ecx
0x180064093  test    dx, dx
0x180064096  jnz     short loc_180064074
0x180064098  btr     r9d, 1Fh
0x18006409d  lea     r8, aSharePermsX; "share perms %x"
0x1800640a4  mov     edx, 1Eh; unsigned __int64
0x1800640a9  lea     rcx, [rbp+60h+Name]; unsigned __int16 *
0x1800640ad  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800640b2  lea     r8, [rbp+60h+Name]; lpName
0x1800640b6  xor     edx, edx; bInitialOwner
0x1800640b8  xor     ecx, ecx; lpMutexAttributes
0x1800640ba  call    cs:__imp_CreateMutexW
0x1800640c0  mov     [rbp+60h+var_B0], rax
0x1800640c4  mov     rbx, rax
0x1800640c7  mov     esi, 1
0x1800640cc  test    rax, rax
0x1800640cf  jz      loc_18006456F
0x1800640d5  mov     edx, 7530h; dwMilliseconds
0x1800640da  mov     rcx, rax; hHandle
0x1800640dd  call    cs:__imp_WaitForSingleObject
0x1800640e3  xor     ecx, ecx
0x1800640e5  test    r14, r14
0x1800640e8  jz      loc_18006455D
0x1800640ee  lea     rax, [rsp+160h+hMem]
0x1800640f3  mov     [rsp+160h+hMem], rcx
0x1800640f8  mov     [rsp+160h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800640fd  lea     r8d, [rsi+3]; SecurityInfo
0x180064101  mov     [rsp+160h+ppSacl], rcx; ppSacl
0x180064106  lea     rax, [rsp+160h+pDacl]
0x18006410b  mov     [rsp+160h+ppDacl], rax; ppDacl
0x180064110  xor     r9d, r9d; ppsidOwner
0x180064113  mov     qword ptr [rsp+160h+fuStyle], rcx; ppsidGroup
0x180064118  mov     edx, esi; ObjectType
0x18006411a  mov     [rsp+160h+pDacl], rcx
0x18006411f  mov     rcx, r12; pObjectName
0x180064122  call    cs:__imp_GetNamedSecurityInfoW
0x180064128  test    eax, eax
0x18006412a  jnz     loc_18006455D
0x180064130  mov     [rbp+60h+var_B8], 0
0x180064138  mov     ebx, 1000h
0x18006413d  test    r13d, r13d
0x180064140  jz      loc_18006420F
0x180064146  mov     rcx, [rsp+160h+pDacl]; pacl
0x18006414b  mov     rdx, r14; StringSid
0x18006414e  call    ?_IsDaclPrivateForUser@@YAHPEAU_ACL@@PEBG@Z; _IsDaclPrivateForUser(_ACL *,ushort const *)
0x180064153  xor     r13d, r13d
0x180064156  test    eax, eax
0x180064158  jz      loc_1800641F3
0x18006415e  test    r15d, r15d
0x180064161  jnz     short loc_180064168
0x180064163  mov     [rbp+60h+var_D0], esi
0x180064166  jmp     short loc_1800641CD
0x180064168  cmp     [rsp+160h+pAccessRights], r13d
0x18006416d  jz      short loc_1800641A8
0x18006416f  mov     rbx, qword ptr [rbp+60h+dwRevision]
0x180064173  test    rbx, rbx
0x180064176  jz      loc_180064212
0x18006417c  mov     rcx, [rsp+160h+hMem]; hMem
0x180064181  call    cs:__imp_LocalFree
0x180064187  mov     rcx, rbx; lpSource
0x18006418a  mov     rdx, r14; unsigned __int16 *
0x18006418d  mov     [rsp+160h+pDacl], r13
0x180064192  lea     r8, [rsp+160h+hMem]; void **
0x180064197  mov     [rsp+160h+hMem], r13
0x18006419c  lea     r9, [rsp+160h+pDacl]; struct _ACL **
0x1800641a1  call    ?_MakeSecurityDescriptorForUser@@YAHPEBG0PEAPEAXPEAPEAU_ACL@@@Z; _MakeSecurityDescriptorForUser(ushort const *,ushort const *,void * *,_ACL * *)
0x1800641a6  jmp     short loc_180064212
0x1800641a8  mov     rcx, [rsp+160h+hMem]; pSecurityDescriptor
0x1800641ad  lea     r8, [rbp+60h+dwRevision]; lpdwRevision
0x1800641b1  lea     rdx, [rsp+160h+pControl]; pControl
0x1800641b6  mov     [rsp+160h+pControl], r13w
0x1800641bc  mov     [rbp+60h+dwRevision], r13d
0x1800641c0  call    cs:__imp_GetSecurityDescriptorControl
0x1800641c6  test    [rsp+160h+pControl], bx
0x1800641cb  jnz     short loc_1800641D7
0x1800641cd  mov     rbx, r13
0x1800641d0  mov     [rsp+160h+pDacl], rbx
0x1800641d5  jmp     short loc_180064217
0x1800641d7  mov     rax, [rsp+160h+pDacl]
0x1800641dc  xor     r8d, r8d; ControlBitsToSet
0x1800641df  mov     edx, ebx; ControlBitsOfInterest
0x1800641e1  mov     [rax+4], r13w
0x1800641e6  mov     rcx, [rsp+160h+hMem]; pSecurityDescriptor
0x1800641eb  call    cs:__imp_SetSecurityDescriptorControl
0x1800641f1  jmp     short loc_180064212
0x1800641f3  test    r15d, r15d
0x1800641f6  jnz     short loc_180064212
0x1800641f8  mov     rcx, [rsp+160h+hMem]; hMem
0x1800641fd  call    cs:__imp_LocalFree
0x180064203  lea     rcx, aDPAOiciGaSyAOi; "D:P(A;OICI;GA;;;SY)(A;OICI;GA;;;%1)"
0x18006420a  jmp     loc_18006418A
0x18006420f  xor     r13d, r13d
0x180064212  mov     rbx, [rsp+160h+pDacl]
0x180064217  mov     r8d, [rbp+60h+var_E0]
0x18006421b  and     r8d, 8
0x18006421f  mov     [rbp+60h+var_E0], r8d
0x180064223  jz      loc_1800642B6
0x180064229  test    rbx, rbx
0x18006422c  jz      loc_180064544
0x180064232  xorps   xmm0, xmm0
0x180064235  mov     [rsp+160h+pAccessRights], r13d
0x18006423a  lea     rdx, qword_180082178; pSid
0x180064241  lea     rcx, [rbp+60h+pTrustee]; pTrustee
0x180064245  movups  xmmword ptr [rbp+60h+pTrustee.pMultipleTrustee], xmm0
0x180064249  movups  xmmword ptr [rbp+60h+pTrustee.TrusteeType], xmm0
0x18006424d  call    cs:__imp_BuildTrusteeWithSidW
0x180064253  lea     r8, [rsp+160h+pAccessRights]; pAccessRights
0x180064258  mov     [rbp+60h+pTrustee.TrusteeType], 5
0x18006425f  lea     rdx, [rbp+60h+pTrustee]; pTrustee
0x180064263  mov     rcx, rbx; pacl
0x180064266  call    cs:__imp_GetEffectiveRightsFromAclW
0x18006426c  mov     rcx, [rsp+160h+hMem]; hMem
0x180064271  call    cs:__imp_LocalFree
0x180064277  test    [rsp+160h+pAccessRights], 0C0000h
0x18006427f  lea     rax, aDPAOiciGaWd; "D:P(A;OICI;GA;;;WD)"
0x180064286  lea     rcx, aDAOiciGaBaAOic; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OI"...
0x18006428d  mov     [rsp+160h+hMem], r13
0x180064292  cmovnz  rcx, rax; lpSource
0x180064296  mov     [rsp+160h+pDacl], r13
0x18006429b  lea     r9, [rsp+160h+pDacl]; struct _ACL **
0x1800642a0  mov     rdx, r14; unsigned __int16 *
0x1800642a3  lea     r8, [rsp+160h+hMem]; void **
0x1800642a8  call    ?_MakeSecurityDescriptorForUser@@YAHPEBG0PEAPEAXPEAPEAU_ACL@@@Z; _MakeSecurityDescriptorForUser(ushort const *,ushort const *,void * *,_ACL * *)
0x1800642ad  mov     r8d, [rbp+60h+var_E0]
0x1800642b1  mov     rbx, [rsp+160h+pDacl]
0x1800642b6  test    rbx, rbx
0x1800642b9  jz      loc_180064544
0x1800642bf  test    r15d, r15d
0x1800642c2  jz      loc_180064432
0x1800642c8  xor     edx, edx
0x1800642ca  lea     r9d, [r15-1]
0x1800642ce  xor     ecx, ecx
0x1800642d0  mov     dword ptr [rsp+160h+pControl], r9d
0x1800642d5  xor     eax, eax
0x1800642d7  mov     [rsp+160h+pAccessRights], edx
0x1800642db  lea     r14, [rbx+8]
0x1800642df  cmp     ax, [rbx+4]
0x1800642e3  jnb     loc_18006438A
0x1800642e9  test    byte ptr [r14+1], 10h
0x1800642ee  jnz     loc_180064381
0x1800642f4  movzx   eax, word ptr [r14+2]
0x1800642f9  add     r13w, si
0x1800642fd  add     ecx, eax
0x1800642ff  mov     [rbp+60h+dwRevision], ecx
0x180064302  test    r8d, r8d
0x180064305  jnz     short loc_180064360
0x180064307  cmp     byte ptr [r14], 3
0x18006430b  ja      short loc_180064360
0x18006430d  lea     rcx, [r14+8]; pSid1
0x180064311  lea     rdx, qword_180082178; pSid2
0x180064318  call    cs:__imp_EqualSid
0x18006431e  mov     edx, [rsp+160h+pAccessRights]
0x180064322  mov     r8d, [rbp+60h+var_E0]
0x180064326  test    eax, eax
0x180064328  jz      short loc_180064358
0x18006432a  mov     ecx, dword ptr [rsp+160h+pControl]
0x18006432e  lea     r10, qword_180082160
0x180064335  xor     r9d, r9d
0x180064338  mov     dword ptr [rsp+160h+pControl], r9d
0x18006433d  mov     al, [r10+rcx*8]
0x180064341  mov     [r14+1], al
0x180064345  mov     eax, [r10+rcx*8+4]
0x18006434a  mov     ecx, [rbp+60h+dwRevision]
0x18006434d  mov     [r14+4], eax
0x180064351  mov     rbx, [rsp+160h+pDacl]
0x180064356  jmp     short loc_180064365
0x180064358  mov     rbx, [rsp+160h+pDacl]
0x18006435d  mov     ecx, [rbp+60h+dwRevision]
0x180064360  mov     r9d, dword ptr [rsp+160h+pControl]
0x180064365  movzx   eax, word ptr [r14+2]
0x18006436a  add     edx, esi
0x18006436c  add     r14, rax
0x18006436f  mov     [rsp+160h+pAccessRights], edx
0x180064373  movzx   eax, word ptr [rbx+4]
0x180064377  cmp     edx, eax
0x180064379  jl      loc_1800642E9
0x18006437f  jmp     short loc_180064386
0x180064381  mov     r9d, dword ptr [rsp+160h+pControl]
0x180064386  mov     rdi, [rbp+60h+var_C8]
  ... truncated ...
```
