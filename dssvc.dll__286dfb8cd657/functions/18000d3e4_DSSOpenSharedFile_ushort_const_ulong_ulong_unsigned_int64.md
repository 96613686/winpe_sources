# DSSOpenSharedFile(ushort const *,ulong,ulong,unsigned __int64 *)

- ea: `0x18000d3e4`
- end: `0x18000d684`
- name: `?DSSOpenSharedFile@@YAJPEBGKKPEA_K@Z`
- size: `672`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, void *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800076f0`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x18000c704`
- `0x18000d3e4`
- `0x18000da68`
- `0x18000ddb8`
- `0x18000f068`
- `0x18000f120`
- `0x18000f1a0`
- `0x18000fcd4`
- `0x18000fd9c`
- `0x180019fe8`
- `0x18001a06c`
- `0x18001a498`
- `0x18001a6f0`
- `0x18001aa74`
- `0x18001ab08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d602`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d602`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d56b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d5f8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d56b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d5f8`

## string_xrefs

- `0x18000d43f`: `Failed to get filehandle for token: %s. hr=0x%x`
- `0x18000d455`: `DSSOpenSharedFile`
- `0x18000d52d`: `VerifyDeleteOnCloseAllowed: FILE_FLAG_DELETE_ON_CLOSE allowed on the shared file!`
- `0x18000d53a`: `DSUtils::VerifyDeleteOnCloseAllowed`
- `0x18000d59b`: `DSUtils::VerifyDeleteOnCloseAllowed`
- `0x18000d58e`: `VerifyDeleteOnCloseAllowed: FILE_FLAG_DELETE_ON_CLOSE is not allowed on the shared file`

## pseudocode

```c
__int64 __fastcall DSSOpenSharedFile(unsigned __int16 *a1, unsigned __int16 *a2, void *a3, unsigned __int64 *a4)
{
  char v4; // r15
  unsigned __int16 *v5; // r13
  int AuthorizedSharingToken; // edi
  DSLogger *v7; // rax
  utl::_RefCountBase *v9; // rsi
  int IsFileEncrypted; // r12d
  DSLogger *v11; // rax
  int v12; // ebx
  bool v13; // zf
  DSLogger *v14; // rax
  unsigned int v15; // eax
  HANDLE *v16; // rax
  void **v17; // r9
  unsigned __int64 v18; // rax
  void **v19; // [rsp+28h] [rbp-38h]
  int v20; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v21; // [rsp+34h] [rbp-2Ch] BYREF
  unsigned __int16 *v22; // [rsp+38h] [rbp-28h] BYREF
  HANDLE hSourceHandle; // [rsp+40h] [rbp-20h] BYREF
  __int64 v24; // [rsp+48h] [rbp-18h] BYREF
  utl::_RefCountBase *v25[2]; // [rsp+50h] [rbp-10h] BYREF
  DWORD dwProcessId; // [rsp+A8h] [rbp+48h]

  dwProcessId = (unsigned int)a2;
  LODWORD(v22) = 0;
  v4 = (char)a3;
  v21 = 0;
  v5 = a1;
  hSourceHandle = (HANDLE)-1LL;
  *(_OWORD *)v25 = 0;
  v24 = -1;
  if ( !dword_18002B2D0 )
  {
    AuthorizedSharingToken = -1055719422;
LABEL_3:
    v7 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                       a1,
                       a2,
                       a3,
                       a4);
    LODWORD(v19) = AuthorizedSharingToken;
    DSLogger::LogError(v7, L"DSSOpenSharedFile", 0x31Eu, L"Failed to get filehandle for token: %s. hr=0x%x", v5, v19);
    goto LABEL_4;
  }
  AuthorizedSharingToken = GetAuthorizedSharingToken(a1);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_3;
  v20 = 0;
  AuthorizedSharingToken = ValidateUsage(v25, &v20);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_3;
  v9 = v25[0];
  a1 = (unsigned __int16 *)*((_QWORD *)v25[0] + 23);
  if ( !a1 )
  {
    AuthorizedSharingToken = -1055719420;
    goto LABEL_3;
  }
  IsFileEncrypted = DSUtils::IsFileEncrypted(a1, a2);
  AuthorizedSharingToken = ShareAccessControl::MapSharePermission(*((unsigned int *)v9 + 30), &v22);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_3;
  AuthorizedSharingToken = ShareAccessControl::MapShareMode(*((unsigned int *)v9 + 31), &v21);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_3;
  if ( (*((_BYTE *)v9 + 120) & 3) != 0 )
  {
    v11 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        a1,
                        a2,
                        a3,
                        a4);
    DSLogger::LogError(
      v11,
      L"DSUtils::VerifyDeleteOnCloseAllowed",
      0x1E9u,
      L"VerifyDeleteOnCloseAllowed: FILE_FLAG_DELETE_ON_CLOSE allowed on the shared file!");
  }
  else if ( (v4 & 2) != 0 )
  {
    v14 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        a1,
                        a2,
                        a3,
                        a4);
    DSLogger::LogError(
      v14,
      L"DSUtils::VerifyDeleteOnCloseAllowed",
      0x1EEu,
      L"VerifyDeleteOnCloseAllowed: FILE_FLAG_DELETE_ON_CLOSE is not allowed on the shared file");
    AuthorizedSharingToken = -2147024891;
    goto LABEL_3;
  }
  v12 = 0;
  v20 = 0;
  if ( IsFileEncrypted )
  {
    AuthorizedSharingToken = AutoImpersonate<2>::ImpersonateCallingUserWithEnterpriseContext(&v20);
    if ( AuthorizedSharingToken < 0 )
    {
      v13 = v20 == 0;
LABEL_18:
      if ( !v13 && !RevertToSelf() )
        GetLastError();
      goto LABEL_3;
    }
    v12 = v20;
  }
  v15 = tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),-1>(&hSourceHandle);
  AuthorizedSharingToken = DSUtils::OpenFile(
                             *((DSUtils **)v9 + 23),
                             (const unsigned __int16 *)(unsigned int)v22,
                             v21,
                             ((unsigned __int8)(v4 & 1) << 30) + 128,
                             v15,
                             v19);
  if ( AuthorizedSharingToken < 0 )
  {
    v13 = v12 == 0;
    goto LABEL_18;
  }
  if ( v12 && !RevertToSelf() )
    GetLastError();
  AuthorizedSharingToken = DSUtils::VerifyFileIdFromHandle(
                             *((wchar_t **)v9 + 27),
                             (const unsigned __int16 *)hSourceHandle,
                             a3);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_3;
  AuthorizedSharingToken = DSUtils::VerifyPathFromHandle(
                             *((wchar_t **)v9 + 23),
                             (const unsigned __int16 *)hSourceHandle,
                             a3);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_3;
  v16 = (HANDLE *)tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),-1>(&v24);
  AuthorizedSharingToken = DSUtils::DuplicateFileHandle(hSourceHandle, dwProcessId, v16, v17);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_3;
  if ( (v4 & 2) != 0 )
    DSUtils::DeleteFileOnClose(hSourceHandle, a2);
  v18 = v24;
  v24 = -1;
  *a4 = v18;
LABEL_4:
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),-1>::_Delete(&v24);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),-1>::_Delete(&hSourceHandle);
  if ( v25[1] )
    utl::_RefCountBase::_DecStrong(v25[1]);
  return (unsigned int)AuthorizedSharingToken;
}

```

## disassembly

```asm
0x18000d3e4  mov     [rsp-38h+arg_0], rbx
0x18000d3e9  mov     [rsp-38h+arg_18], r9
0x18000d3ee  mov     [rsp-38h+dwProcessId], edx
0x18000d3f2  push    rbp
0x18000d3f3  push    rsi
0x18000d3f4  push    rdi
0x18000d3f5  push    r12
0x18000d3f7  push    r13
0x18000d3f9  push    r14
0x18000d3fb  push    r15
0x18000d3fd  mov     rbp, rsp
0x18000d400  sub     rsp, 60h
0x18000d404  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d408  mov     dword ptr [rbp+var_28], 0
0x18000d40f  cmp     cs:dword_18002B2D0, 0
0x18000d416  xorps   xmm0, xmm0
0x18000d419  mov     r15d, r8d
0x18000d41c  mov     [rbp+var_2C], 0
0x18000d423  mov     r13, rcx
0x18000d426  mov     [rbp+hSourceHandle], rax
0x18000d42a  movdqu  xmmword ptr [rbp+var_10], xmm0
0x18000d42f  mov     [rbp+var_18], rax
0x18000d433  jnz     short loc_18000D49E
0x18000d435  mov     edi, 0C1130002h
0x18000d43a  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000d43f  lea     r9, aFailedToGetFil_0; "Failed to get filehandle for token: %s."...
0x18000d446  mov     dword ptr [rsp+60h+var_38], edi
0x18000d44a  mov     r8d, 31Eh; unsigned int
0x18000d450  mov     qword ptr [rsp+60h+var_40], r13
0x18000d455  lea     rdx, aDssopensharedf; "DSSOpenSharedFile"
0x18000d45c  mov     rcx, rax; this
0x18000d45f  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000d464  lea     rcx, [rbp+var_18]
0x18000d468  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1>::_Delete(void)
0x18000d46d  lea     rcx, [rbp+hSourceHandle]
0x18000d471  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1>::_Delete(void)
0x18000d476  mov     rcx, [rbp+var_10+8]; this
0x18000d47a  test    rcx, rcx
0x18000d47d  jz      short loc_18000D484
0x18000d47f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18000d484  mov     rbx, [rsp+60h+arg_0]
0x18000d48c  mov     eax, edi
0x18000d48e  add     rsp, 60h
0x18000d492  pop     r15
0x18000d494  pop     r14
0x18000d496  pop     r13
0x18000d498  pop     r12
0x18000d49a  pop     rdi
0x18000d49b  pop     rsi
0x18000d49c  pop     rbp
0x18000d49d  retn
0x18000d49e  lea     r8, [rbp+var_10]
0x18000d4a2  xor     edx, edx
0x18000d4a4  call    GetAuthorizedSharingToken
0x18000d4a9  mov     edi, eax
0x18000d4ab  test    eax, eax
0x18000d4ad  js      short loc_18000D43A
0x18000d4af  lea     rdx, [rbp+var_30]
0x18000d4b3  mov     [rbp+var_30], 0
0x18000d4ba  lea     rcx, [rbp+var_10]
0x18000d4be  call    ValidateUsage
0x18000d4c3  mov     edi, eax
0x18000d4c5  test    eax, eax
0x18000d4c7  js      loc_18000D43A
0x18000d4cd  mov     rsi, [rbp+var_10]
0x18000d4d1  mov     rcx, [rsi+0B8h]; lpFileName
0x18000d4d8  test    rcx, rcx
0x18000d4db  jnz     short loc_18000D4E7
0x18000d4dd  mov     edi, 0C1130004h
0x18000d4e2  jmp     loc_18000D43A
0x18000d4e7  call    ?IsFileEncrypted@DSUtils@@YAHPEBG@Z; DSUtils::IsFileEncrypted(ushort const *)
0x18000d4ec  mov     ecx, [rsi+78h]
0x18000d4ef  lea     rdx, [rbp+var_28]
0x18000d4f3  mov     r12d, eax
0x18000d4f6  call    ?MapSharePermission@ShareAccessControl@@SAJW4_DS_SHARE_PERMISSION@@PEAK@Z; ShareAccessControl::MapSharePermission(_DS_SHARE_PERMISSION,ulong *)
0x18000d4fb  mov     edi, eax
0x18000d4fd  test    eax, eax
0x18000d4ff  js      loc_18000D43A
0x18000d505  mov     ecx, [rsi+7Ch]
0x18000d508  lea     rdx, [rbp+var_2C]
0x18000d50c  call    ?MapShareMode@ShareAccessControl@@SAJW4_DS_SHARE_MODE@@PEAK@Z; ShareAccessControl::MapShareMode(_DS_SHARE_MODE,ulong *)
0x18000d511  mov     edi, eax
0x18000d513  test    eax, eax
0x18000d515  js      loc_18000D43A
0x18000d51b  mov     r14d, r15d
0x18000d51e  and     r14d, 2
0x18000d522  test    byte ptr [rsi+78h], 3
0x18000d526  jz      short loc_18000D584
0x18000d528  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000d52d  lea     r9, aVerifydeleteon_0; "VerifyDeleteOnCloseAllowed: FILE_FLAG_D"...
0x18000d534  mov     r8d, 1E9h; unsigned int
0x18000d53a  lea     rdx, aDsutilsVerifyd; "DSUtils::VerifyDeleteOnCloseAllowed"
0x18000d541  mov     rcx, rax; this
0x18000d544  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000d549  xor     ebx, ebx
0x18000d54b  mov     [rbp+var_30], ebx
0x18000d54e  test    r12d, r12d
0x18000d551  jz      short loc_18000D5B7
0x18000d553  lea     rcx, [rbp+var_30]
0x18000d557  call    ?ImpersonateCallingUserWithEnterpriseContext@?$AutoImpersonate@$01@@QEAAJXZ; AutoImpersonate<2>::ImpersonateCallingUserWithEnterpriseContext(void)
0x18000d55c  mov     edi, eax
0x18000d55e  test    eax, eax
0x18000d560  jns     short loc_18000D5B4
0x18000d562  cmp     [rbp+var_30], ebx
0x18000d565  jz      loc_18000D43A
0x18000d56b  call    cs:__imp_RevertToSelf
0x18000d571  test    eax, eax
0x18000d573  jnz     loc_18000D43A
0x18000d579  call    cs:__imp_GetLastError
0x18000d57f  jmp     loc_18000D43A
0x18000d584  test    r14d, r14d
0x18000d587  jz      short loc_18000D549
0x18000d589  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000d58e  lea     r9, aVerifydeleteon; "VerifyDeleteOnCloseAllowed: FILE_FLAG_D"...
0x18000d595  mov     r8d, 1EEh; unsigned int
0x18000d59b  lea     rdx, aDsutilsVerifyd; "DSUtils::VerifyDeleteOnCloseAllowed"
0x18000d5a2  mov     rcx, rax; this
0x18000d5a5  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000d5aa  mov     edi, 80070005h
0x18000d5af  jmp     loc_18000D43A
0x18000d5b4  mov     ebx, [rbp+var_30]
0x18000d5b7  lea     rcx, [rbp+hSourceHandle]
0x18000d5bb  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),-1>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1> &)
0x18000d5c0  mov     r8d, [rbp+var_2C]; unsigned int
0x18000d5c4  and     r15d, 1
0x18000d5c8  mov     edx, dword ptr [rbp+var_28]; unsigned __int16 *
0x18000d5cb  mov     rcx, [rsi+0B8h]; this
0x18000d5d2  shl     r15d, 1Eh
0x18000d5d6  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x18000d5db  lea     r9d, [r15+80h]; unsigned int
0x18000d5e2  call    ?OpenFile@DSUtils@@YAJPEBGKKKPEAPEAX@Z; DSUtils::OpenFile(ushort const *,ulong,ulong,ulong,void * *)
0x18000d5e7  mov     edi, eax
0x18000d5e9  test    eax, eax
0x18000d5eb  jns     short loc_18000D5F4
0x18000d5ed  test    ebx, ebx
0x18000d5ef  jmp     loc_18000D565
0x18000d5f4  test    ebx, ebx
0x18000d5f6  jz      short loc_18000D608
0x18000d5f8  call    cs:__imp_RevertToSelf
0x18000d5fe  test    eax, eax
0x18000d600  jnz     short loc_18000D608
0x18000d602  call    cs:__imp_GetLastError
0x18000d608  mov     rdx, [rbp+hSourceHandle]; unsigned __int16 *
0x18000d60c  mov     rcx, [rsi+0D8h]; String2
0x18000d613  call    ?VerifyFileIdFromHandle@DSUtils@@YAJPEBGPEAX@Z; DSUtils::VerifyFileIdFromHandle(ushort const *,void *)
0x18000d618  mov     edi, eax
0x18000d61a  test    eax, eax
0x18000d61c  js      loc_18000D43A
0x18000d622  mov     rdx, [rbp+hSourceHandle]; unsigned __int16 *
0x18000d626  mov     rcx, [rsi+0B8h]; String2
0x18000d62d  call    ?VerifyPathFromHandle@DSUtils@@YAJPEBGPEAX@Z; DSUtils::VerifyPathFromHandle(ushort const *,void *)
0x18000d632  mov     edi, eax
0x18000d634  test    eax, eax
0x18000d636  js      loc_18000D43A
0x18000d63c  lea     rcx, [rbp+var_18]
0x18000d640  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),-1>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1> &)
0x18000d645  mov     edx, [rbp+dwProcessId]; dwProcessId
0x18000d648  mov     r8, rax; lpTargetHandle
0x18000d64b  mov     rcx, [rbp+hSourceHandle]; hSourceHandle
0x18000d64f  call    ?DuplicateFileHandle@DSUtils@@YAJPEAXKPEAPEAX@Z; DSUtils::DuplicateFileHandle(void *,ulong,void * *)
0x18000d654  mov     edi, eax
0x18000d656  test    eax, eax
0x18000d658  js      loc_18000D43A
0x18000d65e  test    r14d, r14d
0x18000d661  jz      short loc_18000D66C
0x18000d663  mov     rcx, [rbp+hSourceHandle]; hFile
0x18000d667  call    ?DeleteFileOnClose@DSUtils@@YAJPEAX@Z; DSUtils::DeleteFileOnClose(void *)
0x18000d66c  mov     rax, [rbp+var_18]
0x18000d670  mov     rcx, [rbp+arg_18]
0x18000d674  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFFh
0x18000d67c  mov     [rcx], rax
0x18000d67f  jmp     loc_18000D464
```
