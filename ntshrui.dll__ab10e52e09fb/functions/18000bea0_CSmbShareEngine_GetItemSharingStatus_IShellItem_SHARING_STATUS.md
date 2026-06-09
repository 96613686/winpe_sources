# CSmbShareEngine::GetItemSharingStatus(IShellItem *,SHARING_STATUS *)

- ea: `0x18000bea0`
- end: `0x18000c6e1`
- name: `?GetItemSharingStatus@CSmbShareEngine@@UEAAJPEAUIShellItem@@PEAW4SHARING_STATUS@@@Z`
- size: `2113`
- prototype: `__int64 __fastcall(CSmbShareEngine *__hidden this, struct IShellItem *, enum SHARING_STATUS *)`
- caller_count: `0`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b6f0`
- `0x18000bdc0`
- `0x18000bea0`
- `0x18000d1f0`
- `0x18000dd60`
- `0x18000f7a0`
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

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c528`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c55c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c528`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c55c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4ab`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000c1dd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000c1dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c20b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c20b`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x18000c04c`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x18000c04c`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000c638`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000c638`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c0c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c2f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c39e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c0c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c2f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c39e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000bfde`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000bfde`
- `SHCORE!SHStrDupW` at `0x18000c0b9`
- `SHCORE!SHStrDupW` at `0x18000c0b9`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x18000c0db`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x18000c0db`
- `SHLWAPI!StrChrW` at `0x18000c5c7`
- `SHLWAPI!StrChrW` at `0x18000c5f1`
- `SHLWAPI!StrChrW` at `0x18000c5c7`
- `SHLWAPI!StrChrW` at `0x18000c5f1`
- `SHLWAPI!PathRemoveBackslashW` at `0x18000c0a2`
- `SHLWAPI!PathRemoveBackslashW` at `0x18000c0a2`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18000c146`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18000c146`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSmbShareEngine::GetItemSharingStatus(
        CSmbShareEngine *this,
        struct IShellItem *a2,
        enum SHARING_STATUS *a3)
{
  enum SHARING_STATUS *v3; // r14
  int v5; // r15d
  int NonSystemAceList; // r12d
  int v7; // ebx
  WCHAR *v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rcx
  WCHAR *v11; // rdx
  __int64 v12; // rsi
  __int64 v13; // r8
  WCHAR *v14; // r9
  WCHAR v15; // ax
  WCHAR *v16; // rcx
  WCHAR *v17; // rdx
  WCHAR v18; // ax
  WCHAR *v19; // rcx
  HRESULT v20; // ebx
  const WCHAR *v21; // rcx
  struct CAceList *v22; // rdi
  int v23; // r15d
  signed int NamedSecurityInfoW; // eax
  unsigned int v25; // edx
  int v26; // r8d
  WCHAR *v27; // rsi
  struct _ACL *v28; // r14
  CAceList *v29; // rbx
  unsigned int v30; // edx
  BOOL v31; // r14d
  WCHAR *v32; // rbx
  int i; // r15d
  int *v34; // rsi
  int v35; // eax
  int j; // r15d
  int *v37; // rsi
  int v38; // eax
  LPWSTR v39; // rcx
  int v40; // ebx
  int v41; // eax
  FARPROC v43; // rax
  struct CAce *v44; // rsi
  FARPROC ProcAddress; // rax
  struct CAce *v46; // rsi
  signed int LastError; // eax
  HMODULE v48; // rcx
  HMODULE v49; // rcx
  const WCHAR *v50; // r15
  PWSTR v51; // rax
  const unsigned __int16 *v52; // r14
  const WCHAR *v53; // rbx
  PWSTR v54; // rax
  const WCHAR *v55; // rax
  CShareCache *v56; // rcx
  int v57; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR ppszServer; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-B0h] BYREF
  enum SHARING_STATUS *v60; // [rsp+60h] [rbp-A0h]
  DWORD dwRevision[2]; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR ppwsz; // [rsp+70h] [rbp-90h] BYREF
  PACL ppDacl; // [rsp+78h] [rbp-88h] BYREF
  PSID ppsidOwner; // [rsp+80h] [rbp-80h] BYREF
  CAceList *v65; // [rsp+88h] [rbp-78h]
  CSmbShareEngine *v66; // [rsp+90h] [rbp-70h]
  WCHAR psz[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR pszPath[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v3 = a3;
  v60 = a3;
  v66 = this;
  v5 = 0;
  v57 = 0;
  ppwsz = 0;
  pv[0] = 0;
  *(_QWORD *)dwRevision = 0;
  ppszServer = 0;
  if ( ((int (__fastcall *)(struct IShellItem *, _QWORD, const GUID *, GUID *, PCWSTR *))a2->lpVtbl->BindToHandler)(
         a2,
         0,
         &BHID_SFObject,
         &GUID_7d903fca_d6f9_4810_8332_946c0177e247,
         &ppszServer) >= 0 )
  {
    ppDacl = 0;
    v7 = (*(__int64 (__fastcall **)(PCWSTR, PACL *))(*(_QWORD *)ppszServer + 32LL))(ppszServer, &ppDacl);
    if ( v7 >= 0 )
    {
      v7 = (**(__int64 (__fastcall ***)(PACL, GUID *, DWORD *))ppDacl)(
             ppDacl,
             &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
             dwRevision);
      (*(void (__fastcall **)(PACL))(*(_QWORD *)ppDacl + 16LL))(ppDacl);
    }
    (*(void (__fastcall **)(PCWSTR))(*(_QWORD *)ppszServer + 16LL))(ppszServer);
    if ( v7 >= 0 )
      goto LABEL_7;
  }
  NonSystemAceList = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, DWORD *))a2->lpVtbl->QueryInterface)(
                       a2,
                       &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                       dwRevision);
  if ( NonSystemAceList >= 0 )
  {
LABEL_7:
    NonSystemAceList = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID *))(**(_QWORD **)dwRevision + 40LL))(
                         *(_QWORD *)dwRevision,
                         2147844096LL,
                         pv);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)dwRevision + 16LL))(*(_QWORD *)dwRevision);
  }
  if ( NonSystemAceList >= 0 )
  {
    v8 = (WCHAR *)pv[0];
    psz[0] = 0;
    InitOnceExecuteOnce(&InitOnce, OneTimeInit, 0, 0);
    v9 = 2147483646;
    v10 = 2147483646;
    v11 = v8;
    v12 = 260;
    v13 = 260;
    v14 = pszPath;
    do
    {
      if ( !v10 )
        break;
      v15 = *v11;
      if ( !*v11 )
        break;
      ++v11;
      *v14++ = v15;
      --v10;
      --v13;
    }
    while ( v13 );
    v16 = v14 - 1;
    if ( v13 )
      v16 = v14;
    *v16 = 0;
    if ( !v13 )
      goto LABEL_119;
    ppszServer = 0;
    if ( PathIsUNCEx(pszPath, &ppszServer) )
    {
      v50 = ppszServer;
      v51 = StrChrW(ppszServer, 0x5Cu);
      if ( v51 )
      {
        *v51 = 0;
        v52 = v51 + 1;
        if ( v51[1] )
        {
          v53 = 0;
          v54 = StrChrW(v51 + 1, 0x5Cu);
          if ( v54 )
          {
            *v54 = 0;
            v55 = v54 + 1;
            if ( *v55 )
              v53 = v55;
          }
          if ( !(unsigned int)SHIsThisComputerByNameOnly(v50) || !CShareCache::IsExistingShare(v56, v52, psz, 260) )
          {
            v5 = 0;
            v3 = v60;
            goto LABEL_119;
          }
          if ( !v53 )
          {
            v3 = v60;
            v5 = 0;
            goto LABEL_26;
          }
          v20 = PathCchAppend(psz, 0x104u, v53);
          v3 = v60;
          v5 = 0;
LABEL_25:
          if ( !v20 )
          {
LABEL_26:
            NonSystemAceList = SHStrDupW(psz, &ppwsz);
            CoTaskMemFree(pv[0]);
            if ( NonSystemAceList < 0 )
              goto LABEL_62;
            v21 = ppwsz;
LABEL_28:
            if ( PathIsNetworkPathW(v21) || !(unsigned int)CFolderAclEngine::s_DoesVolumeSupportFileSystemAcls(ppwsz) )
              goto LABEL_62;
            v22 = 0;
            v65 = 0;
            v23 = (int)ppwsz;
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
              goto LABEL_121;
            v27 = (WCHAR *)ppszServer;
            v28 = ppDacl;
            NonSystemAceList = -2147024882;
            v29 = (CAceList *)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
            *(_QWORD *)dwRevision = v29;
            if ( !v29 )
            {
LABEL_41:
              LocalFree((HLOCAL)ppszServer);
              if ( NonSystemAceList >= 0 )
              {
                ppszServer = 0;
                LODWORD(pv[0]) = 0;
                v31 = ((int (__fastcall *)(struct IShellItem *, __int64, LPVOID *))a2->lpVtbl->GetAttributes)(
                        a2,
                        1614807040,
                        pv) >= 0
                   && LODWORD(pv[0]) == 1610612736;
                NonSystemAceList = CFolderAclEngine::_s_GetNonSystemAceList(v22, v31, (struct CAceList **)&ppszServer);
                v32 = (WCHAR *)ppszServer;
                if ( NonSystemAceList >= 0 && !CAceList::DoesAceListHasMoreThanOneSidForAllow((CAceList *)ppszServer) )
                {
                  for ( i = 0; ; ++i )
                  {
                    v34 = (int *)*((_QWORD *)v32 + 1);
                    if ( v34 )
                      v35 = *v34;
                    else
                      v35 = 0;
                    if ( i >= v35 )
                    {
                      for ( j = 0; ; ++j )
                      {
                        v37 = (int *)*((_QWORD *)v32 + 2);
                        if ( v37 )
                          v38 = *v37;
                        else
                          v38 = 0;
                        if ( j >= v38 )
                        {
                          v57 = 1;
                          goto LABEL_56;
                        }
                        ProcAddress = (FARPROC)qword_180095A20;
                        if ( qword_180095A20 == (__int64 (__fastcall *)(_QWORD, _QWORD))-1LL )
                        {
                          v49 = g_hinstCC;
                          if ( !g_hinstCC )
                          {
                            DelayLoadCC();
                            v49 = g_hinstCC;
                            if ( !g_hinstCC )
                            {
                              qword_180095A20 = 0;
LABEL_103:
                              v46 = 0;
                              goto LABEL_87;
                            }
                          }
                          ProcAddress = GetProcAddress(v49, (LPCSTR)0x14C);
                          qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))ProcAddress;
                        }
                        if ( !ProcAddress )
                          goto LABEL_103;
                        v46 = (struct CAce *)((__int64 (__fastcall *)(int *, _QWORD))ProcAddress)(v37, j);
LABEL_87:
                        if ( !(unsigned int)CFolderAclEngine::_s_IsSystemAce(v46, v31)
                          && !(unsigned int)CAce::IsUser(v46) )
                        {
                          goto LABEL_56;
                        }
                      }
                    }
                    v43 = (FARPROC)qword_180095A20;
                    if ( qword_180095A20 == (__int64 (__fastcall *)(_QWORD, _QWORD))-1LL )
                    {
                      v48 = g_hinstCC;
                      if ( !g_hinstCC )
                      {
                        DelayLoadCC();
                        v48 = g_hinstCC;
                        if ( !g_hinstCC )
                        {
                          qword_180095A20 = 0;
LABEL_101:
                          v44 = 0;
                          goto LABEL_81;
                        }
                      }
                      v43 = GetProcAddress(v48, (LPCSTR)0x14C);
                      qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))v43;
                    }
                    if ( !v43 )
                      goto LABEL_101;
                    v44 = (struct CAce *)((__int64 (__fastcall *)(int *, _QWORD))v43)(v34, i);
LABEL_81:
                    if ( !(unsigned int)CFolderAclEngine::_s_IsSystemAce(v44, v31) && !(unsigned int)CAce::IsUser(v44) )
                      break;
                  }
                }
LABEL_56:
                if ( v32 )
                  CAceList::`scalar deleting destructor'((CAceList *)v32, v25);
                v3 = v60;
                goto LABEL_59;
              }
              v3 = v60;
LABEL_121:
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v26, v23, NonSystemAceList);
              }
              if ( NonSystemAceList == -2147024891 )
              {
                NonSystemAceList = 0;
                v5 = 0;
LABEL_60:
                if ( v22 )
                  CAceList::`scalar deleting destructor'(v22, v25);
                goto LABEL_62;
              }
LABEL_59:
              v5 = v57;
              goto LABEL_60;
            }
            *(_QWORD *)v29 = 0;
            *((_QWORD *)v29 + 1) = 0;
            *((_QWORD *)v29 + 2) = 0;
            *((_QWORD *)v29 + 3) = 1;
            NonSystemAceList = CAceList::_InitFromAcl(v29, v28);
            if ( NonSystemAceList >= 0 && v27 )
            {
              LOWORD(pv[0]) = 0;
              dwRevision[0] = 0;
              if ( GetSecurityDescriptorControl(v27, (PSECURITY_DESCRIPTOR_CONTROL)pv, dwRevision) )
              {
                if ( ((__int64)pv[0] & 0x1000) != 0 )
                  *((_DWORD *)v29 + 6) = 0;
                *((_DWORD *)v29 + 7) = 0;
LABEL_40:
                v22 = v29;
                v65 = v29;
                goto LABEL_41;
              }
              LastError = GetLastError();
              NonSystemAceList = LastError;
              if ( LastError > 0 )
                NonSystemAceList = (unsigned __int16)LastError | 0x80070000;
            }
            if ( NonSystemAceList < 0 )
            {
              CAceList::`scalar deleting destructor'(v29, v30);
              goto LABEL_41;
            }
            goto LABEL_40;
          }
LABEL_119:
          v21 = (const WCHAR *)pv[0];
          ppwsz = (LPWSTR)pv[0];
          goto LABEL_28;
        }
        v3 = v60;
        v5 = 0;
      }
      else
      {
        v5 = v57;
      }
    }
    v17 = psz;
    do
    {
      if ( !v9 )
        break;
      v18 = *v8;
      if ( !*v8 )
        break;
      ++v8;
      *v17++ = v18;
      --v9;
      --v12;
    }
    while ( v12 );
    v19 = v17 - 1;
    if ( v12 )
      v19 = v17;
    *v19 = 0;
    v20 = -2147024774;
    if ( v12 )
    {
      v20 = 0;
      PathRemoveBackslashW(psz);
    }
    goto LABEL_25;
  }
LABEL_62:
  v39 = ppwsz;
  ppwsz = 0;
  CoTaskMemFree(v39);
  if ( NonSystemAceList >= 0 )
  {
    if ( v5 )
    {
      v41 = 2;
      goto LABEL_72;
    }
    v57 = 0;
    if ( ((int (__fastcall *)(struct IShellItem *, __int64, int *))a2->lpVtbl->GetAttributes)(a2, 1614807040, &v57) >= 0
      && v57 == 1610612736 )
    {
      v40 = 0;
      ppszServer = 0;
      NonSystemAceList = ((__int64 (__fastcall *)(struct IShellItem *, __int64, PCWSTR *))a2->lpVtbl->GetDisplayName)(
                           a2,
                           2147844096LL,
                           &ppszServer);
      if ( NonSystemAceList >= 0 )
      {
        v57 = 0;
        NonSystemAceList = (*(__int64 (__fastcall **)(_QWORD, PCWSTR, __int64, int *))(**((_QWORD **)v66 + 6) + 48LL))(
                             *((_QWORD *)v66 + 6),
                             ppszServer,
                             1,
                             &v57);
        if ( NonSystemAceList >= 0 )
          v40 = v57;
        CoTaskMemFree((LPVOID)ppszServer);
      }
      if ( NonSystemAceList >= 0 && v40 )
      {
        v41 = 1;
        goto LABEL_72;
      }
    }
    else
    {
      NonSystemAceList = -2147467263;
    }
  }
  v41 = 0;
LABEL_72:
  *(_DWORD *)v3 = v41;
  return (unsigned int)NonSystemAceList;
}

```

## disassembly

```asm
0x18000bea0  mov     [rsp-8+arg_18], rbx
0x18000bea5  push    rbp
0x18000bea6  push    rsi
0x18000bea7  push    rdi
0x18000bea8  push    r12
0x18000beaa  push    r13
0x18000beac  push    r14
0x18000beae  push    r15
0x18000beb0  lea     rbp, [rsp-3D0h]
0x18000beb8  sub     rsp, 4D0h
0x18000bebf  mov     rax, cs:__security_cookie
0x18000bec6  xor     rax, rsp
0x18000bec9  mov     [rbp+400h+var_40], rax
0x18000bed0  mov     r14, r8
0x18000bed3  mov     [rsp+500h+var_4A0], r8
0x18000bed8  mov     r13, rdx
0x18000bedb  mov     [rbp+400h+var_470], rcx
0x18000bedf  xor     edi, edi
0x18000bee1  mov     r15d, edi
0x18000bee4  mov     [rsp+500h+var_4C0], edi
0x18000bee8  mov     [rsp+500h+ppwsz], rdi
0x18000beed  mov     [rsp+500h+pv], rdi
0x18000bef2  mov     qword ptr [rsp+500h+dwRevision], rdi
0x18000bef7  mov     [rsp+500h+ppszServer], rdi
0x18000befc  mov     rax, [rdx]
0x18000beff  lea     rcx, [rsp+500h+ppszServer]
0x18000bf04  mov     [rsp+500h+ppsidGroup], rcx
0x18000bf09  lea     r9, _GUID_7d903fca_d6f9_4810_8332_946c0177e247
0x18000bf10  lea     r8, BHID_SFObject
0x18000bf17  xor     edx, edx
0x18000bf19  mov     rcx, r13
0x18000bf1c  mov     rax, [rax+18h]
0x18000bf20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf25  test    eax, eax
0x18000bf27  jns     short loc_18000BF4D
0x18000bf29  mov     rax, [r13+0]
0x18000bf2d  lea     r8, [rsp+500h+dwRevision]
0x18000bf32  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18000bf39  mov     rcx, r13
0x18000bf3c  mov     rax, [rax]
0x18000bf3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf44  mov     r12d, eax
0x18000bf47  test    eax, eax
0x18000bf49  js      short loc_18000BFB6
0x18000bf4b  jmp     short loc_18000BF87
0x18000bf4d  mov     [rsp+500h+var_488], rdi
0x18000bf52  mov     rcx, [rsp+500h+ppszServer]
0x18000bf57  mov     rax, [rcx]
0x18000bf5a  lea     rdx, [rsp+500h+var_488]
0x18000bf5f  mov     rax, [rax+20h]
0x18000bf63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf68  mov     ebx, eax
0x18000bf6a  test    eax, eax
0x18000bf6c  jns     loc_18000C4D2
0x18000bf72  mov     rcx, [rsp+500h+ppszServer]
0x18000bf77  mov     rax, [rcx]
0x18000bf7a  mov     rax, [rax+10h]
0x18000bf7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf83  test    ebx, ebx
0x18000bf85  js      short loc_18000BF29
0x18000bf87  mov     rcx, qword ptr [rsp+500h+dwRevision]
0x18000bf8c  mov     rax, [rcx]
0x18000bf8f  lea     r8, [rsp+500h+pv]
0x18000bf94  mov     edx, 80058000h
0x18000bf99  mov     rax, [rax+28h]
0x18000bf9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfa2  mov     r12d, eax
0x18000bfa5  mov     rcx, qword ptr [rsp+500h+dwRevision]
0x18000bfaa  mov     rax, [rcx]
0x18000bfad  mov     rax, [rax+10h]
0x18000bfb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfb6  test    r12d, r12d
0x18000bfb9  js      loc_18000C2E6
0x18000bfbf  mov     rdi, [rsp+500h+pv]
0x18000bfc4  xor     eax, eax
0x18000bfc6  mov     [rbp+400h+psz], ax
0x18000bfca  xor     r9d, r9d; Context
0x18000bfcd  xor     r8d, r8d; Parameter
0x18000bfd0  lea     rdx, _OneTimeInit; InitFn
0x18000bfd7  lea     rcx, InitOnce; InitOnce
0x18000bfde  call    cs:__imp_InitOnceExecuteOnce
0x18000bfe4  mov     ebx, 7FFFFFFEh
0x18000bfe9  mov     ecx, ebx
0x18000bfeb  mov     rdx, rdi
0x18000bfee  mov     esi, 104h
0x18000bff3  mov     r8d, esi
0x18000bff6  lea     r9, [rbp+400h+pszPath]
0x18000bffd  nop     dword ptr [rax]
0x18000c000  test    rcx, rcx
0x18000c003  jz      short loc_18000C022
0x18000c005  movzx   eax, word ptr [rdx]
0x18000c008  test    ax, ax
0x18000c00b  jz      short loc_18000C022
0x18000c00d  add     rdx, 2
0x18000c011  mov     [r9], ax
0x18000c015  add     r9, 2
0x18000c019  dec     rcx
0x18000c01c  sub     r8, 1
0x18000c020  jnz     short loc_18000C000
0x18000c022  lea     rcx, [r9-2]
0x18000c026  test    r8, r8
0x18000c029  cmovnz  rcx, r9
0x18000c02d  xor     eax, eax
0x18000c02f  mov     [rcx], ax
0x18000c032  test    r8, r8
0x18000c035  jz      loc_18000C679
0x18000c03b  mov     [rsp+500h+ppszServer], rax
0x18000c040  lea     rdx, [rsp+500h+ppszServer]; ppszServer
0x18000c045  lea     rcx, [rbp+400h+pszPath]; pszPath
0x18000c04c  call    cs:__imp_PathIsUNCEx
0x18000c052  test    eax, eax
0x18000c054  jnz     loc_18000C5BA
0x18000c05a  lea     rdx, [rbp+400h+psz]
0x18000c05e  xchg    ax, ax
0x18000c060  test    rbx, rbx
0x18000c063  jz      short loc_18000C081
0x18000c065  movzx   eax, word ptr [rdi]
0x18000c068  test    ax, ax
0x18000c06b  jz      short loc_18000C081
0x18000c06d  add     rdi, 2
0x18000c071  mov     [rdx], ax
0x18000c074  add     rdx, 2
0x18000c078  dec     rbx
0x18000c07b  sub     rsi, 1
0x18000c07f  jnz     short loc_18000C060
0x18000c081  lea     rcx, [rdx-2]
0x18000c085  test    rsi, rsi
0x18000c088  cmovnz  rcx, rdx
0x18000c08c  xor     eax, eax
0x18000c08e  mov     [rcx], ax
0x18000c091  mov     ebx, 8007007Ah
0x18000c096  test    rsi, rsi
0x18000c099  cmovnz  ebx, eax
0x18000c09c  jz      short loc_18000C0A8
0x18000c09e  lea     rcx, [rbp+400h+psz]; pszPath
0x18000c0a2  call    cs:__imp_PathRemoveBackslashW
0x18000c0a8  test    ebx, ebx
0x18000c0aa  jnz     loc_18000C679
0x18000c0b0  lea     rdx, [rsp+500h+ppwsz]; ppwsz
0x18000c0b5  lea     rcx, [rbp+400h+psz]; psz
0x18000c0b9  call    cs:__imp_SHStrDupW
0x18000c0bf  mov     r12d, eax
0x18000c0c2  mov     rcx, [rsp+500h+pv]; pv
0x18000c0c7  call    cs:__imp_CoTaskMemFree
0x18000c0cd  test    r12d, r12d
0x18000c0d0  js      loc_18000C2E6
0x18000c0d6  mov     rcx, [rsp+500h+ppwsz]; pszPath
0x18000c0db  call    cs:__imp_PathIsNetworkPathW
0x18000c0e1  test    eax, eax
0x18000c0e3  jnz     loc_18000C2E6
0x18000c0e9  mov     rcx, [rsp+500h+ppwsz]; unsigned __int16 *
0x18000c0ee  call    ?s_DoesVolumeSupportFileSystemAcls@CFolderAclEngine@@SAHPEBG@Z; CFolderAclEngine::s_DoesVolumeSupportFileSystemAcls(ushort const *)
0x18000c0f3  test    eax, eax
0x18000c0f5  jz      loc_18000C2E6
0x18000c0fb  xor     esi, esi
0x18000c0fd  mov     edi, esi
0x18000c0ff  mov     [rbp+400h+var_478], rsi
0x18000c103  mov     r15, [rsp+500h+ppwsz]
0x18000c108  mov     [rsp+500h+ppszServer], rsi
0x18000c10d  mov     [rsp+500h+var_488], rsi
0x18000c112  mov     [rbp+400h+ppsidOwner], rsi
0x18000c116  lea     rax, [rsp+500h+ppszServer]
0x18000c11b  mov     [rsp+500h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18000c120  mov     [rsp+500h+ppSacl], rsi; ppSacl
0x18000c125  lea     rax, [rsp+500h+var_488]
0x18000c12a  mov     [rsp+500h+ppDacl], rax; ppDacl
0x18000c12f  mov     [rsp+500h+ppsidGroup], rsi; ppsidGroup
0x18000c134  lea     r9, [rbp+400h+ppsidOwner]; ppsidOwner
0x18000c138  mov     edx, 1; ObjectType
0x18000c13d  mov     r8d, 5; SecurityInfo
0x18000c143  mov     rcx, r15; pObjectName
0x18000c146  call    cs:__imp_GetNamedSecurityInfoW
0x18000c14c  mov     r12d, eax
0x18000c14f  test    eax, eax
0x18000c151  jg      loc_18000C3DB
0x18000c157  test    r12d, r12d
0x18000c15a  js      loc_18000C696
0x18000c160  mov     rsi, [rsp+500h+ppszServer]
0x18000c165  mov     r14, [rsp+500h+var_488]
0x18000c16a  mov     r12d, 8007000Eh
0x18000c170  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c177  mov     ecx, 20h ; ' '; unsigned __int64
0x18000c17c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c181  mov     rbx, rax
0x18000c184  mov     qword ptr [rsp+500h+dwRevision], rax
0x18000c189  test    rax, rax
0x18000c18c  jz      short loc_18000C206
0x18000c18e  xor     eax, eax
0x18000c190  mov     [rbx], rax
0x18000c193  mov     [rbx+8], rax
0x18000c197  mov     [rbx+10h], rax
0x18000c19b  mov     qword ptr [rbx+18h], 1
0x18000c1a3  mov     rdx, r14; struct _ACL *
0x18000c1a6  mov     rcx, rbx; this
0x18000c1a9  call    ?_InitFromAcl@CAceList@@AEAAJPEAU_ACL@@@Z; CAceList::_InitFromAcl(_ACL *)
0x18000c1ae  mov     r12d, eax
0x18000c1b1  test    eax, eax
0x18000c1b3  js      loc_18000C4BC
0x18000c1b9  test    rsi, rsi
0x18000c1bc  jz      loc_18000C4BC
0x18000c1c2  xor     r14d, r14d
0x18000c1c5  mov     word ptr [rsp+500h+pv], r14w
0x18000c1cb  mov     [rsp+500h+dwRevision], r14d
0x18000c1d0  lea     r8, [rsp+500h+dwRevision]; lpdwRevision
0x18000c1d5  lea     rdx, [rsp+500h+pv]; pControl
0x18000c1da  mov     rcx, rsi; pSecurityDescriptor
0x18000c1dd  call    cs:__imp_GetSecurityDescriptorControl
0x18000c1e3  test    eax, eax
0x18000c1e5  jz      loc_18000C4AB
0x18000c1eb  mov     eax, 1000h
0x18000c1f0  test    word ptr [rsp+500h+pv], ax
0x18000c1f5  jnz     loc_18000C688
0x18000c1fb  mov     [rbx+1Ch], r14d
0x18000c1ff  mov     rdi, rbx
0x18000c202  mov     [rbp+400h+var_478], rbx
0x18000c206  mov     rcx, [rsp+500h+ppszServer]; hMem
0x18000c20b  call    cs:__imp_LocalFree
0x18000c211  xor     esi, esi
0x18000c213  test    r12d, r12d
0x18000c216  js      loc_18000C691
0x18000c21c  mov     [rsp+500h+ppszServer], rsi
0x18000c221  mov     dword ptr [rsp+500h+pv], esi
0x18000c225  mov     rax, [r13+0]
0x18000c229  lea     r8, [rsp+500h+pv]
0x18000c22e  mov     edx, 60400000h
0x18000c233  mov     rcx, r13
0x18000c236  mov     rax, [rax+30h]
0x18000c23a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c23f  test    eax, eax
0x18000c241  js      loc_18000C3FE
0x18000c247  cmp     dword ptr [rsp+500h+pv], 60000000h
0x18000c24f  jnz     loc_18000C3FE
0x18000c255  mov     r14d, 1
0x18000c25b  lea     r8, [rsp+500h+ppszServer]; struct CAceList **
0x18000c260  mov     edx, r14d; int
0x18000c263  mov     rcx, rdi; struct CAceList *
0x18000c266  call    ?_s_GetNonSystemAceList@CFolderAclEngine@@CAJPEAVCAceList@@HPEAPEAV2@@Z; CFolderAclEngine::_s_GetNonSystemAceList(CAceList *,int,CAceList * *)
0x18000c26b  mov     r12d, eax
0x18000c26e  mov     rbx, [rsp+500h+ppszServer]
0x18000c273  test    eax, eax
0x18000c275  js      short loc_18000C2C1
0x18000c277  mov     rcx, rbx; this
0x18000c27a  call    ?DoesAceListHasMoreThanOneSidForAllow@CAceList@@QEAA_NXZ; CAceList::DoesAceListHasMoreThanOneSidForAllow(void)
0x18000c27f  test    al, al
0x18000c281  jnz     short loc_18000C2C1
0x18000c283  mov     r15d, esi
0x18000c286  mov     rsi, [rbx+8]
0x18000c28a  test    rsi, rsi
0x18000c28d  jz      loc_18000C6D2
0x18000c293  mov     eax, [rsi]
0x18000c295  cmp     r15d, eax
0x18000c298  jl      loc_18000C40D
0x18000c29e  xor     r15d, r15d
0x18000c2a1  mov     rsi, [rbx+10h]
0x18000c2a5  test    rsi, rsi
0x18000c2a8  jz      loc_18000C6D9
0x18000c2ae  mov     eax, [rsi]
0x18000c2b0  cmp     r15d, eax
0x18000c2b3  jl      loc_18000C45C
0x18000c2b9  mov     [rsp+500h+var_4C0], 1
0x18000c2c1  test    rbx, rbx
0x18000c2c4  jz      short loc_18000C2CE
0x18000c2c6  mov     rcx, rbx; this
0x18000c2c9  call    ??_GCAceList@@QEAAPEAXI@Z; CAceList::`scalar deleting destructor'(uint)
0x18000c2ce  mov     r14, [rsp+500h+var_4A0]
0x18000c2d3  mov     r15d, [rsp+500h+var_4C0]
0x18000c2d8  test    rdi, rdi
0x18000c2db  jz      short loc_18000C2E6
0x18000c2dd  mov     rcx, rdi; this
0x18000c2e0  call    ??_GCAceList@@QEAAPEAXI@Z; CAceList::`scalar deleting destructor'(uint)
0x18000c2e5  nop
0x18000c2e6  mov     rcx, [rsp+500h+ppwsz]; pv
0x18000c2eb  xor     edi, edi
0x18000c2ed  mov     [rsp+500h+ppwsz], rdi
0x18000c2f2  call    cs:__imp_CoTaskMemFree
0x18000c2f8  test    r12d, r12d
0x18000c2fb  js      loc_18000C3A9
0x18000c301  test    r15d, r15d
0x18000c304  jnz     loc_18000C406
0x18000c30a  mov     [rsp+500h+var_4C0], edi
0x18000c30e  mov     rax, [r13+0]
0x18000c312  lea     r8, [rsp+500h+var_4C0]
0x18000c317  mov     edx, 60400000h
0x18000c31c  mov     rcx, r13
0x18000c31f  mov     rax, [rax+30h]
0x18000c323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c328  test    eax, eax
0x18000c32a  js      loc_18000C3EB
0x18000c330  cmp     [rsp+500h+var_4C0], 60000000h
0x18000c338  jnz     loc_18000C3EB
0x18000c33e  mov     ebx, edi
0x18000c340  mov     [rsp+500h+ppszServer], rdi
0x18000c345  mov     rax, [r13+0]
0x18000c349  lea     r8, [rsp+500h+ppszServer]
0x18000c34e  mov     edx, 80058000h
0x18000c353  mov     rcx, r13
0x18000c356  mov     rax, [rax+28h]
0x18000c35a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c35f  mov     r12d, eax
0x18000c362  test    eax, eax
  ... truncated ...
```
