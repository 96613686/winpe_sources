# UserAccountNode::CreateLocalAccountWithUserManager(void)

- ea: `0x180025224`
- end: `0x180025d39`
- name: `?CreateLocalAccountWithUserManager@UserAccountNode@@AEAAJXZ`
- size: `2837`
- prototype: `__int64 __fastcall(UserAccountNode *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024ba0`

## callees

- `0x180006954`
- `0x180006974`
- `0x180009eb0`
- `0x180025224`
- `0x180025dd8`
- `0x18003586a`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800252d3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002561a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800252d3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002561a`
- `samcli!NetUserSetInfo` at `0x180025855`
- `samcli!NetUserSetInfo` at `0x180025855`
- `samcli!NetLocalGroupAddMembers` at `0x180025bcc`
- `samcli!NetLocalGroupAddMembers` at `0x180025bcc`
- `samcli!NetUserGetInfo` at `0x1800256e2`
- `samcli!NetUserGetInfo` at `0x18002590b`
- `samcli!NetUserGetInfo` at `0x1800256e2`
- `samcli!NetUserGetInfo` at `0x18002590b`
- `netutils!NetApiBufferFree` at `0x18002571d`
- `netutils!NetApiBufferFree` at `0x1800257ba`
- `netutils!NetApiBufferFree` at `0x180025890`
- `netutils!NetApiBufferFree` at `0x180025946`
- `netutils!NetApiBufferFree` at `0x18002595c`
- `netutils!NetApiBufferFree` at `0x180025a1f`
- `netutils!NetApiBufferFree` at `0x180025a35`
- `netutils!NetApiBufferFree` at `0x180025b2e`
- `netutils!NetApiBufferFree` at `0x180025b44`
- `netutils!NetApiBufferFree` at `0x180025c07`
- `netutils!NetApiBufferFree` at `0x180025c1d`
- `netutils!NetApiBufferFree` at `0x180025c8d`
- `netutils!NetApiBufferFree` at `0x180025ca3`
- `netutils!NetApiBufferFree` at `0x18002571d`
- `netutils!NetApiBufferFree` at `0x1800257ba`
- `netutils!NetApiBufferFree` at `0x180025890`
- `netutils!NetApiBufferFree` at `0x180025946`
- `netutils!NetApiBufferFree` at `0x18002595c`
- `netutils!NetApiBufferFree` at `0x180025a1f`
- `netutils!NetApiBufferFree` at `0x180025a35`
- `netutils!NetApiBufferFree` at `0x180025b2e`
- `netutils!NetApiBufferFree` at `0x180025b44`
- `netutils!NetApiBufferFree` at `0x180025c07`
- `netutils!NetApiBufferFree` at `0x180025c1d`
- `netutils!NetApiBufferFree` at `0x180025c8d`
- `netutils!NetApiBufferFree` at `0x180025ca3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800252b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025633`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800252b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025633`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002530e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002530e`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18002525d`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18002525d`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180025d07`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180025d07`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180025af6`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180025af6`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800259e7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800259e7`

## string_xrefs

- `0x180025554`: `Other user already exists.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall UserAccountNode::CreateLocalAccountWithUserManager(UserAccountNode *this)
{
  int v2; // eax
  unsigned int LastError; // ebx
  int ActivationFactory; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  const WCHAR *v21; // rbx
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // r14
  __int64 (__fastcall *v23)(_QWORD, GUID *, __int64 *); // r15
  unsigned __int64 v24; // rdi
  int v25; // eax
  unsigned int v26; // edi
  __int64 v27; // rcx
  __int64 v28; // rcx
  DWORD Info; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  _QWORD *v35; // rcx
  DWORD v36; // eax
  __int64 v37; // rcx
  __int64 v38; // rcx
  DWORD v39; // eax
  __int64 v40; // rcx
  __int64 v41; // rcx
  const char *v42; // r9
  __int64 v43; // rcx
  __int64 v44; // rcx
  const char *v45; // r9
  __int64 v46; // rcx
  __int64 v47; // rcx
  DWORD v48; // eax
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  unsigned int parm_err; // [rsp+20h] [rbp-E0h]
  unsigned int parm_erra; // [rsp+20h] [rbp-E0h]
  unsigned int parm_errb; // [rsp+20h] [rbp-E0h]
  const char *cchReferencedDomainName; // [rsp+28h] [rbp-D8h]
  __int64 (__fastcall ***v58)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-C0h] BYREF
  __int64 v59; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v60; // [rsp+50h] [rbp-B0h] BYREF
  LPBYTE bufptr; // [rsp+58h] [rbp-A8h] BYREF
  LPBYTE v62; // [rsp+60h] [rbp-A0h] BYREF
  int v63; // [rsp+68h] [rbp-98h] BYREF
  char v64; // [rsp+6Dh] [rbp-93h]
  int v65; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbSid; // [rsp+74h] [rbp-8Ch] BYREF
  enum _SID_NAME_USE peUse; // [rsp+78h] [rbp-88h] BYREF
  DWORD v68; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD cchName; // [rsp+80h] [rbp-80h] BYREF
  BYTE buf[8]; // [rsp+88h] [rbp-78h] BYREF
  HSTRING string; // [rsp+90h] [rbp-70h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-68h] BYREF
  HSTRING v73; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING_HEADER v74; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR ReferencedDomainName[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v76; // [rsp+E0h] [rbp-20h]
  _BYTE pSid[80]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR Name[264]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+2A8h]

  v2 = RoInitialize(1);
  LastError = v2;
  if ( v2 >= 0 )
  {
    v64 = 1;
    v58 = 0;
    v59 = 0;
    if ( WindowsCreateStringReference(L"Windows.System.Internal.UserManager", 0x23u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    ActivationFactory = RoGetActivationFactory(string, &GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9, &v58);
    LastError = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
      v9 = **v58;
      v10 = v59;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      v11 = v9(v8, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v59);
      LastError = v11;
      if ( v11 >= 0 )
      {
        v60 = 0;
        v13 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v58)[11])(
                v58,
                &v60);
        LastError = v13;
        if ( v13 >= 0 )
        {
          v63 = 0;
          v16 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v60 + 56LL))(v60, &v63);
          LastError = v16;
          if ( v16 >= 0 )
          {
            if ( v63 )
            {
              LastError = -2147024891;
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0xDA,
                (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
                (const char *)0x80070005LL,
                (int)"Other user already exists.",
                cchReferencedDomainName);
              v19 = v60;
              if ( v60 )
              {
                v60 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
              }
              v20 = v59;
              if ( v59 )
              {
                v59 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
              }
              v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
              if ( v58 )
              {
                v58 = 0;
                ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v7)[2])(v7);
              }
            }
            else
            {
              v65 = 0;
              v21 = (const WCHAR *)((char *)this + 24);
              if ( *((_QWORD *)this + 6) >= 8u )
                v21 = *(const WCHAR **)v21;
              v22 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
              v23 = (*v58)[7];
              v24 = -1;
              do
                ++v24;
              while ( v21[v24] );
              if ( v24 > 0xFFFFFFFF )
              {
                LODWORD(v24) = -1;
                RaiseException(0xC000000D, 1u, 0, 0);
              }
              WindowsCreateStringReference(v21, v24, &v74, &v73);
              v25 = v23(v22, (GUID *)v73, (__int64 *)&v65);
              v26 = v25;
              if ( v25 >= 0 )
              {
                bufptr = 0;
                Info = NetUserGetInfo(0, v21, 1u, &bufptr);
                if ( Info )
                {
                  LastError = wil::details::in1diag3::Return_Win32(
                                retaddr,
                                (void *)0xE6,
                                (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
                                (const char *)Info,
                                parm_err);
                  if ( bufptr )
                    NetApiBufferFree(bufptr);
                  v30 = v60;
                  if ( v60 )
                  {
                    v60 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
                  }
                  v31 = v59;
                  if ( v59 )
                  {
                    v59 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                  }
                  v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
                  if ( v58 )
                  {
                    v58 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v7)[2])(v7);
                  }
                }
                else
                {
                  v32 = *((_QWORD *)this + 8);
                  if ( v32 )
                  {
                    v35 = (_QWORD *)(v32 + 24);
                    if ( v35[3] >= 8u )
                      v35 = (_QWORD *)*v35;
                    *((_QWORD *)bufptr + 1) = v35;
                    *((_DWORD *)bufptr + 10) = 66048;
                    v36 = NetUserSetInfo(0, v21, 1u, bufptr, 0);
                    if ( v36 )
                    {
                      LastError = wil::details::in1diag3::Return_Win32(
                                    retaddr,
                                    (void *)0xF3,
                                    (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
                                    (const char *)v36,
                                    parm_erra);
                      if ( bufptr )
                        NetApiBufferFree(bufptr);
                      v37 = v60;
                      if ( v60 )
                      {
                        v60 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                      }
                      v38 = v59;
                      if ( v59 )
                      {
                        v59 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
                      }
                      v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
                      if ( v58 )
                      {
                        v58 = 0;
                        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v7)[2])(v7);
                      }
                    }
                    else
                    {
                      v62 = 0;
                      v39 = NetUserGetInfo(0, v21, 4u, &v62);
                      if ( v39 )
                      {
                        LastError = wil::details::in1diag3::Return_Win32(
                                      retaddr,
                                      (void *)0xF7,
                                      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
                                      (const char *)v39,
                                      parm_erra);
                        if ( v62 )
                          NetApiBufferFree(v62);
                        if ( bufptr )
                          NetApiBufferFree(bufptr);
                        v40 = v60;
                        if ( v60 )
                        {
                          v60 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
                        }
                        v41 = v59;
                        if ( v59 )
                        {
                          v59 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                        }
                        v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
                        if ( v58 )
                        {
                          v58 = 0;
                          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v7)[2])(v7);
                        }
                      }
                      else
                      {
                        memset_0(pSid, 0, 0x44u);
                        cbSid = 68;
                        if ( CreateWellKnownSid(WinAuthenticationAuthorityAssertedSid|WinSelfSid, 0, pSid, &cbSid) )
                        {
                          cchName = 256;
                          memset_0(Name, 0, 0x202u);
                          v68 = 15;
                          *(_OWORD *)ReferencedDomainName = 0;
                          v76 = 0;
                          peUse = 0;
                          if ( LookupAccountSidW(0, pSid, Name, &cchName, ReferencedDomainName, &v68, &peUse) )
                          {
                            *(_QWORD *)buf = *((_QWORD *)v62 + 19);
                            v48 = NetLocalGroupAddMembers(0, Name, 0, buf, 1u);
                            if ( v48 )
                            {
                              LastError = wil::details::in1diag3::Return_Win32(
                                            retaddr,
                                            (void *)0x109,
                                            (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
                                            (const char *)v48,
                                            parm_errb);
                              if ( v62 )
                                NetApiBufferFree(v62);
                              if ( bufptr )
                                NetApiBufferFree(bufptr);
                              v49 = v60;
                              if ( v60 )
                              {
                                v60 = 0;
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
                              }
                              v50 = v59;
                              if ( v59 )
                              {
                                v59 = 0;
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
                              }
                              v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
                              if ( v58 )
                              {
                                v58 = 0;
                                ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v7)[2])(v7);
                              }
                            }
                            else
                            {
                              if ( v62 )
                                NetApiBufferFree(v62);
                              if ( bufptr )
                                NetApiBufferFree(bufptr);
                              v51 = v60;
                              if ( v60 )
                              {
                                v60 = 0;
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
                              }
                              v52 = v59;
                              if ( v59 )
                              {
                                v59 = 0;
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
                              }
                              v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
                              if ( v58 )
                              {
                                v58 = 0;
                                ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v7)[2])(v7);
                              }
                              LastError = 0;
                            }
                          }
                          else
                          {
                            LastError = wil::details::in1diag3::Return_GetLastError(
                                          retaddr,
                                          (void *)0x104,
                                          (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
                                          v45);
                            if ( v62 )
                              NetApiBufferFree(v62);
                            if ( bufptr )
                              NetApiBufferFree(bufptr);
                            v46 = v60;
                            if ( v60 )
                            {
                              v60 = 0;
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
                            }
                            v47 = v59;
                            if ( v59 )
                            {
                              v59 = 0;
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
                            }
                            v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
                            if ( v58 )
                            {
                              v58 = 0;
                              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v7)[2])(v7);
                            }
                          }
                        }
                        else
                        {
                          LastError = wil::details::in1diag3::Return_GetLastError(
                                        retaddr,
                                        (void *)0xFC,
                                        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
                                        v42);
                          if ( v62 )
                            NetApiBufferFree(v62);
                          if ( bufptr )
                            NetApiBufferFree(bufptr);
                          v43 = v60;
                          if ( v60 )
                          {
                            v60 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
                          }
                          v44 = v59;
                          if ( v59 )
                          {
                            v59 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
                          }
                          v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
                          if ( v58 )
                          {
                            v58 = 0;
                            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v7)[2])(v7);
                          }
                        }
                      }
                    }
                  }
                  else
                  {
                    LastError = -2147024809;
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xEE,
                      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
                      (const char *)0x80070057LL,
                      parm_err);
                    if ( bufptr )
                      NetApiBufferFree(bufptr);
                    v33 = v60;
                    if ( v60 )
                    {
                      v60 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                    }
                    v34 = v59;
                    if ( v59 )
                    {
                      v59 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                    }
                    v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
                    if ( v58 )
                    {
                      v58 = 0;
                      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v7)[2])(v7);
                    }
                  }
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xE2,
                  (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
                  (const char *)(unsigned int)v25,
                  parm_err);
                v27 = v60;
                if ( v60 )
                {
                  v60 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
                }
                v28 = v59;
                if ( v59 )
                {
                  v59 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                }
                v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
                if ( v58 )
                {
                  v58 = 0;
                  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v7)[2])(v7);
                }
                LastError = v26;
              }
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xD9,
              (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
              (const char *)(unsigned int)v16,
              parm_err);
            v17 = v60;
            if ( v60 )
            {
              v60 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            }
            v18 = v59;
            if ( v59 )
            {
              v59 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            }
            v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
            if ( v58 )
            {
              v58 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v7)[2])(v7);
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD7,
            (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
            (const char *)(unsigned int)v13,
            parm_err);
          v14 = v60;
          if ( v60 )
          {
            v60 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          }
          v15 = v59;
          if ( v59 )
          {
            v59 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          }
          v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
          if ( v58 )
          {
            v58 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v7)[2])(v7);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD2,
          (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
          (const char *)(unsigned int)v11,
          parm_err);
        v12 = v59;
        if ( v59 )
        {
          v59 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        }
        v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
        if ( v58 )
        {
          v58 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v7)[2])(v7);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD1,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
        (const char *)(unsigned int)ActivationFactory,
        parm_err);
      v6 = v59;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      }
      v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
      if ( v58 )
      {
        v58 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v7)[2])(v7);
      }
    }
    RoUninitialize(v7, v5);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
      (const char *)(unsigned int)v2,
      parm_err);
  }
  return LastError;
}

```

## disassembly

```asm
0x180025224  push    rbp
0x180025226  push    rbx
0x180025227  push    rsi
0x180025228  push    rdi
0x180025229  push    r12
0x18002522b  push    r13
0x18002522d  push    r14
0x18002522f  push    r15
0x180025231  lea     rbp, [rsp-268h]
0x180025239  sub     rsp, 368h
0x180025240  mov     rax, cs:__security_cookie
0x180025247  xor     rax, rsp
0x18002524a  mov     [rbp+2A0h+var_50], rax
0x180025251  mov     rsi, rcx
0x180025254  mov     r13d, 1
0x18002525a  mov     ecx, r13d
0x18002525d  call    cs:__imp_RoInitialize
0x180025264  nop     dword ptr [rax+rax+00h]
0x180025269  mov     ebx, eax
0x18002526b  xor     r12d, r12d
0x18002526e  test    eax, eax
0x180025270  jns     short loc_180025292
0x180025272  mov     rcx, [rbp+2A8h]; this
0x180025279  mov     r9d, eax; char *
0x18002527c  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provcsp\\usera"...
0x180025283  mov     edx, 0C7h; void *
0x180025288  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002528d  jmp     loc_180025D13
0x180025292  mov     [rsp+3A0h+var_333], r13b
0x180025297  mov     [rsp+3A0h+var_360], r12
0x18002529c  mov     [rsp+3A0h+var_358], r12
0x1800252a1  lea     r9, [rbp+2A0h+string]; string
0x1800252a5  lea     r8, [rbp+2A0h+hstringHeader]; hstringHeader
0x1800252a9  mov     edx, 23h ; '#'; length
0x1800252ae  lea     rcx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x1800252b5  call    cs:__imp_WindowsCreateStringReference
0x1800252bc  nop     dword ptr [rax+rax+00h]
0x1800252c1  test    eax, eax
0x1800252c3  jns     short loc_1800252DF
0x1800252c5  xor     r9d, r9d; lpArguments
0x1800252c8  xor     r8d, r8d; nNumberOfArguments
0x1800252cb  mov     edx, r13d; dwExceptionFlags
0x1800252ce  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800252d3  call    cs:__imp_RaiseException
0x1800252da  nop     dword ptr [rax+rax+00h]
0x1800252df  mov     rbx, [rbp+2A0h+string]
0x1800252e3  mov     rcx, [rsp+3A0h+var_360]
0x1800252e8  test    rcx, rcx
0x1800252eb  jz      short loc_1800252FF
0x1800252ed  mov     [rsp+3A0h+var_360], r12
0x1800252f2  mov     rax, [rcx]
0x1800252f5  mov     rax, [rax+10h]
0x1800252f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252fe  nop
0x1800252ff  lea     r8, [rsp+3A0h+var_360]
0x180025304  lea     rdx, _GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9
0x18002530b  mov     rcx, rbx
0x18002530e  call    cs:__imp_RoGetActivationFactory
0x180025315  nop     dword ptr [rax+rax+00h]
0x18002531a  mov     ebx, eax
0x18002531c  test    eax, eax
0x18002531e  jns     short loc_180025379
0x180025320  mov     rcx, [rbp+2A8h]; this
0x180025327  mov     r9d, eax; char *
0x18002532a  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provcsp\\usera"...
0x180025331  mov     edx, 0D1h; void *
0x180025336  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002533b  nop
0x18002533c  mov     rcx, [rsp+3A0h+var_358]
0x180025341  test    rcx, rcx
0x180025344  jz      short loc_180025358
0x180025346  mov     [rsp+3A0h+var_358], r12
0x18002534b  mov     rax, [rcx]
0x18002534e  mov     rax, [rax+10h]
0x180025352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025357  nop
0x180025358  mov     rcx, [rsp+3A0h+var_360]
0x18002535d  test    rcx, rcx
0x180025360  jz      short loc_180025374
0x180025362  mov     [rsp+3A0h+var_360], r12
0x180025367  mov     rax, [rcx]
0x18002536a  mov     rax, [rax+10h]
0x18002536e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025373  nop
0x180025374  jmp     loc_180025D07
0x180025379  mov     rbx, [rsp+3A0h+var_360]
0x18002537e  mov     rax, [rbx]
0x180025381  mov     rdi, [rax]
0x180025384  mov     rcx, [rsp+3A0h+var_358]
0x180025389  test    rcx, rcx
0x18002538c  jz      short loc_1800253A0
0x18002538e  mov     [rsp+3A0h+var_358], r12
0x180025393  mov     rdx, [rcx]
0x180025396  mov     rax, [rdx+10h]
0x18002539a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002539f  nop
0x1800253a0  lea     r8, [rsp+3A0h+var_358]
0x1800253a5  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x1800253ac  mov     rcx, rbx
0x1800253af  mov     rax, rdi
0x1800253b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253b7  mov     ebx, eax
0x1800253b9  test    eax, eax
0x1800253bb  jns     short loc_180025416
0x1800253bd  mov     rcx, [rbp+2A8h]; this
0x1800253c4  mov     r9d, eax; char *
0x1800253c7  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provcsp\\usera"...
0x1800253ce  mov     edx, 0D2h; void *
0x1800253d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800253d8  nop
0x1800253d9  mov     rcx, [rsp+3A0h+var_358]
0x1800253de  test    rcx, rcx
0x1800253e1  jz      short loc_1800253F5
0x1800253e3  mov     [rsp+3A0h+var_358], r12
0x1800253e8  mov     rax, [rcx]
0x1800253eb  mov     rax, [rax+10h]
0x1800253ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253f4  nop
0x1800253f5  mov     rcx, [rsp+3A0h+var_360]
0x1800253fa  test    rcx, rcx
0x1800253fd  jz      short loc_180025411
0x1800253ff  mov     [rsp+3A0h+var_360], r12
0x180025404  mov     rax, [rcx]
0x180025407  mov     rax, [rax+10h]
0x18002540b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025410  nop
0x180025411  jmp     loc_180025D07
0x180025416  mov     [rsp+3A0h+var_350], r12
0x18002541b  mov     rcx, [rsp+3A0h+var_360]
0x180025420  mov     rax, [rcx]
0x180025423  lea     rdx, [rsp+3A0h+var_350]
0x180025428  mov     rax, [rax+58h]
0x18002542c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025431  mov     ebx, eax
0x180025433  test    eax, eax
0x180025435  jns     short loc_1800254AC
0x180025437  mov     rcx, [rbp+2A8h]; this
0x18002543e  mov     r9d, eax; char *
0x180025441  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provcsp\\usera"...
0x180025448  mov     edx, 0D7h; void *
0x18002544d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025452  nop
0x180025453  mov     rcx, [rsp+3A0h+var_350]
0x180025458  test    rcx, rcx
0x18002545b  jz      short loc_18002546F
0x18002545d  mov     [rsp+3A0h+var_350], r12
0x180025462  mov     rax, [rcx]
0x180025465  mov     rax, [rax+10h]
0x180025469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002546e  nop
0x18002546f  mov     rcx, [rsp+3A0h+var_358]
0x180025474  test    rcx, rcx
0x180025477  jz      short loc_18002548B
0x180025479  mov     [rsp+3A0h+var_358], r12
0x18002547e  mov     rax, [rcx]
0x180025481  mov     rax, [rax+10h]
0x180025485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002548a  nop
0x18002548b  mov     rcx, [rsp+3A0h+var_360]
0x180025490  test    rcx, rcx
0x180025493  jz      short loc_1800254A7
0x180025495  mov     [rsp+3A0h+var_360], r12
0x18002549a  mov     rax, [rcx]
0x18002549d  mov     rax, [rax+10h]
0x1800254a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254a6  nop
0x1800254a7  jmp     loc_180025D07
0x1800254ac  mov     [rsp+3A0h+var_338], r12d
0x1800254b1  mov     rcx, [rsp+3A0h+var_350]
0x1800254b6  mov     rax, [rcx]
0x1800254b9  lea     rdx, [rsp+3A0h+var_338]
0x1800254be  mov     rax, [rax+38h]
0x1800254c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254c7  mov     ebx, eax
0x1800254c9  test    eax, eax
0x1800254cb  jns     short loc_180025542
0x1800254cd  mov     rcx, [rbp+2A8h]; this
0x1800254d4  mov     r9d, eax; char *
0x1800254d7  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provcsp\\usera"...
0x1800254de  mov     edx, 0D9h; void *
0x1800254e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800254e8  nop
0x1800254e9  mov     rcx, [rsp+3A0h+var_350]
0x1800254ee  test    rcx, rcx
0x1800254f1  jz      short loc_180025505
0x1800254f3  mov     [rsp+3A0h+var_350], r12
0x1800254f8  mov     rax, [rcx]
0x1800254fb  mov     rax, [rax+10h]
0x1800254ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025504  nop
0x180025505  mov     rcx, [rsp+3A0h+var_358]
0x18002550a  test    rcx, rcx
0x18002550d  jz      short loc_180025521
0x18002550f  mov     [rsp+3A0h+var_358], r12
0x180025514  mov     rax, [rcx]
0x180025517  mov     rax, [rax+10h]
0x18002551b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025520  nop
0x180025521  mov     rcx, [rsp+3A0h+var_360]
0x180025526  test    rcx, rcx
0x180025529  jz      short loc_18002553D
0x18002552b  mov     [rsp+3A0h+var_360], r12
0x180025530  mov     rax, [rcx]
0x180025533  mov     rax, [rax+10h]
0x180025537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002553c  nop
0x18002553d  jmp     loc_180025D07
0x180025542  cmp     [rsp+3A0h+var_338], r12d
0x180025547  jbe     loc_1800255D3
0x18002554d  mov     rcx, [rbp+2A8h]; this
0x180025554  lea     rax, aOtherUserAlrea; "Other user already exists."
0x18002555b  mov     [rsp+3A0h+parm_err], rax; int
0x180025560  mov     ebx, 80070005h
0x180025565  mov     r9d, ebx; char *
0x180025568  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provcsp\\usera"...
0x18002556f  mov     edx, 0DAh; void *
0x180025574  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180025579  nop
0x18002557a  mov     rcx, [rsp+3A0h+var_350]
0x18002557f  test    rcx, rcx
0x180025582  jz      short loc_180025596
0x180025584  mov     [rsp+3A0h+var_350], r12
0x180025589  mov     rax, [rcx]
0x18002558c  mov     rax, [rax+10h]
0x180025590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025595  nop
0x180025596  mov     rcx, [rsp+3A0h+var_358]
0x18002559b  test    rcx, rcx
0x18002559e  jz      short loc_1800255B2
0x1800255a0  mov     [rsp+3A0h+var_358], r12
0x1800255a5  mov     rax, [rcx]
0x1800255a8  mov     rax, [rax+10h]
0x1800255ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255b1  nop
0x1800255b2  mov     rcx, [rsp+3A0h+var_360]
0x1800255b7  test    rcx, rcx
0x1800255ba  jz      short loc_1800255CE
0x1800255bc  mov     [rsp+3A0h+var_360], r12
0x1800255c1  mov     rax, [rcx]
0x1800255c4  mov     rax, [rax+10h]
0x1800255c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255cd  nop
0x1800255ce  jmp     loc_180025D07
0x1800255d3  mov     [rsp+3A0h+var_330], r12d
0x1800255d8  lea     rbx, [rsi+18h]
0x1800255dc  cmp     qword ptr [rbx+18h], 8
0x1800255e1  jb      short loc_1800255E6
0x1800255e3  mov     rbx, [rbx]
0x1800255e6  mov     r14, [rsp+3A0h+var_360]
0x1800255eb  mov     rax, [r14]
0x1800255ee  mov     r15, [rax+38h]
0x1800255f2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800255f6  inc     rdi
0x1800255f9  cmp     [rbx+rdi*2], r12w
0x1800255fe  jnz     short loc_1800255F6
0x180025600  mov     eax, 0FFFFFFFFh
0x180025605  cmp     rdi, rax
0x180025608  jbe     short loc_180025626
0x18002560a  mov     edi, eax
0x18002560c  xor     r9d, r9d; lpArguments
0x18002560f  xor     r8d, r8d; nNumberOfArguments
0x180025612  mov     edx, r13d; dwExceptionFlags
0x180025615  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002561a  call    cs:__imp_RaiseException
0x180025621  nop     dword ptr [rax+rax+00h]
0x180025626  lea     r9, [rbp+2A0h+var_2F0]; string
0x18002562a  lea     r8, [rbp+2A0h+var_2E8]; hstringHeader
0x18002562e  mov     edx, edi; length
0x180025630  mov     rcx, rbx; sourceString
0x180025633  call    cs:__imp_WindowsCreateStringReference
0x18002563a  nop     dword ptr [rax+rax+00h]
0x18002563f  lea     r8, [rsp+3A0h+var_330]
0x180025644  mov     rdx, [rbp+2A0h+var_2F0]
0x180025648  mov     rcx, r14
0x18002564b  mov     rax, r15
0x18002564e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025653  mov     edi, eax
0x180025655  test    eax, eax
0x180025657  jns     short loc_1800256D0
0x180025659  mov     rcx, [rbp+2A8h]; this
0x180025660  mov     r9d, eax; char *
0x180025663  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provcsp\\usera"...
0x18002566a  mov     edx, 0E2h; void *
0x18002566f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025674  nop
0x180025675  mov     rcx, [rsp+3A0h+var_350]
0x18002567a  test    rcx, rcx
0x18002567d  jz      short loc_180025691
0x18002567f  mov     [rsp+3A0h+var_350], r12
0x180025684  mov     rax, [rcx]
0x180025687  mov     rax, [rax+10h]
0x18002568b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025690  nop
0x180025691  mov     rcx, [rsp+3A0h+var_358]
0x180025696  test    rcx, rcx
0x180025699  jz      short loc_1800256AD
0x18002569b  mov     [rsp+3A0h+var_358], r12
0x1800256a0  mov     rax, [rcx]
0x1800256a3  mov     rax, [rax+10h]
0x1800256a7  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
