# SrvCreateProtectedRootSubKey

- ea: `0x1800e0d10`
- end: `0x1800e11d8`
- name: `SrvCreateProtectedRootSubKey`
- size: `1224`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, HKEY hKey)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b2730`

## callees

- `0x18000fd10`
- `0x180028d60`
- `0x180030e60`
- `0x180046e10`
- `0x1800df150`
- `0x1800e0d10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0d9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0e06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0fe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e10d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e113c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0d9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0e06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0fe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e10d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e113c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e0d97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e0e00`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e1121`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e11a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e0d97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e0e00`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e1121`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e11a8`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800e0f66`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800e0f66`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1800e1103`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1800e1103`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800e0d7d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800e0d7d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e0df4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e0df4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e116d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e116d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e0e30`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e0e30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e0e1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e0e1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e117c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e117c`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800e0f20`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800e0f20`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800e0db3`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800e0db3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e115a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e115a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800e0e5c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800e0e6b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800e0e7a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800e0e5c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800e0e6b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800e0e7a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800e0ea4`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800e0ea4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800e0ec4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800e0ee2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800e0eff`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800e0ec4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800e0ee2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800e0eff`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800e0fd7`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800e1080`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800e0fd7`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800e1080`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800e109a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800e109a`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800e10cd`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800e10cd`
- `RPCRT4!RpcRevertToSelf` at `0x1800e1152`
- `RPCRT4!RpcRevertToSelf` at `0x1800e1152`
- `RPCRT4!RpcImpersonateClient` at `0x1800e0d8b`
- `RPCRT4!RpcImpersonateClient` at `0x1800e0d8b`

## pseudocode

```c
__int64 __fastcall SrvCreateProtectedRootSubKey(RPC_BINDING_HANDLE BindingHandle, HKEY hKey, _DWORD *a3)
{
  _DWORD *v4; // r13
  PSID *v6; // r12
  void *v7; // rsi
  struct _ACL *v8; // r14
  void *v9; // r15
  RPC_STATUS v10; // eax
  DWORD LastError; // ebx
  unsigned int v12; // edi
  int v13; // r13d
  LSTATUS v14; // eax
  HANDLE CurrentThread; // rax
  PSID *TokenInfo; // rax
  PSID v17; // r12
  DWORD LengthSid; // ebx
  DWORD v19; // ebx
  DWORD v20; // ebx
  struct _ACL *v21; // rax
  DWORD i; // ebx
  LSTATUS KeySecurity; // eax
  __int64 v24; // rax
  char *v25; // rax
  __int64 v26; // rax
  DWORD v27; // ecx
  __int64 result; // rax
  PSID *v29; // [rsp+68h] [rbp-19h]
  DWORD dwOwnerSize; // [rsp+70h] [rbp-11h] BYREF
  DWORD dwSaclSize; // [rsp+74h] [rbp-Dh] BYREF
  DWORD dwDaclSize; // [rsp+78h] [rbp-9h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+7Ch] [rbp-5h] BYREF
  DWORD dwDisposition; // [rsp+80h] [rbp-1h] BYREF
  HKEY hKeya; // [rsp+88h] [rbp+7h] BYREF
  void *TokenHandle; // [rsp+90h] [rbp+Fh] BYREF
  LPVOID pAce; // [rsp+98h] [rbp+17h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+100h] [rbp+7Fh] BYREF

  dwDisposition = 2;
  hKeya = 0;
  v4 = a3;
  TokenHandle = 0;
  cbSecurityDescriptor = 0;
  pAce = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  v6 = 0;
  dwPrimaryGroupSize = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  RegDeleteKeyExW(hKey, L"Software\\Microsoft\\SystemCertificates\\Root\\ProtectedRoots", 0, 0);
  if ( BindingHandle )
  {
    v10 = RpcImpersonateClient(BindingHandle);
    if ( v10 )
    {
      SetLastError(v10);
      LastError = GetLastError();
      v12 = 0;
      goto LABEL_47;
    }
  }
  else
  {
    v13 = 0;
    if ( !ImpersonateSelf(SecurityImpersonation) )
      goto LABEL_42;
  }
  v14 = RegCreateKeyExW(
          hKey,
          L"Software\\Microsoft\\SystemCertificates\\Root\\ProtectedRoots",
          0,
          0,
          0,
          0x60000u,
          0,
          &hKeya,
          &dwDisposition);
  if ( v14 )
  {
    SetLastError(v14);
    LastError = GetLastError();
    v12 = 0;
    goto LABEL_43;
  }
  v13 = 1;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    TokenInfo = (PSID *)AllocAndGetTokenInfo(TokenHandle, TokenUser);
    v29 = TokenInfo;
    if ( TokenInfo )
    {
      v17 = *TokenInfo;
      LengthSid = GetLengthSid(*TokenInfo);
      v19 = GetLengthSid(pSid) + LengthSid;
      v20 = GetLengthSid(Sid) + 32 + v19;
      v21 = (struct _ACL *)PkiNonzeroAlloc(v20);
      v8 = v21;
      if ( !v21 )
        goto LABEL_39;
      if ( InitializeAcl(v21, v20, 2u) )
      {
        if ( AddAccessAllowedAce(v8, 2u, 0xF003Fu, Sid)
          && AddAccessAllowedAce(v8, 2u, 0x20019u, v17)
          && AddAccessAllowedAce(v8, 2u, 0x20019u, pSid) )
        {
          for ( i = 0; i < 3; ++i )
          {
            if ( !GetAce(v8, i, &pAce) )
              goto LABEL_39;
            *((_BYTE *)pAce + 1) = 2;
          }
          cbSecurityDescriptor = 1024;
          v7 = (void *)PkiZeroAlloc(0x400u);
          if ( v7 )
          {
            while ( 1 )
            {
              KeySecurity = RegGetKeySecurity(hKeya, 0x80000004, v7, &cbSecurityDescriptor);
              LastError = KeySecurity;
              if ( !KeySecurity )
                break;
              if ( KeySecurity != 122 )
                goto LABEL_34;
              v24 = PkiRealloc(v7, cbSecurityDescriptor);
              if ( !v24 )
                goto LABEL_39;
              v7 = (void *)v24;
            }
            cbSecurityDescriptor = 0;
            if ( MakeAbsoluteSD(
                   v7,
                   0,
                   &cbSecurityDescriptor,
                   0,
                   &dwDaclSize,
                   0,
                   &dwSaclSize,
                   0,
                   &dwOwnerSize,
                   0,
                   &dwPrimaryGroupSize) )
            {
              v27 = 1359;
              goto LABEL_38;
            }
            if ( GetLastError() == 122 )
            {
              v25 = (char *)PkiZeroAlloc(cbSecurityDescriptor + dwDaclSize
                                                              + dwSaclSize
                                                              + dwPrimaryGroupSize
                                                              + dwOwnerSize);
              v9 = v25;
              if ( v25 )
              {
                if ( MakeAbsoluteSD(
                       v7,
                       v25,
                       &cbSecurityDescriptor,
                       (PACL)&v25[cbSecurityDescriptor],
                       &dwDaclSize,
                       (PACL)&v25[dwDaclSize + (unsigned __int64)cbSecurityDescriptor],
                       &dwSaclSize,
                       &v25[cbSecurityDescriptor + dwSaclSize + (unsigned __int64)dwDaclSize],
                       &dwOwnerSize,
                       &v25[cbSecurityDescriptor + dwDaclSize + dwSaclSize + (unsigned __int64)dwOwnerSize],
                       &dwPrimaryGroupSize) )
                {
                  if ( !SetSecurityDescriptorDacl(v9, 1, v8, 0) )
                    goto LABEL_40;
                  PkiDefaultCryptFree(v7);
                  cbSecurityDescriptor = 1024;
                  v7 = (void *)PkiZeroAlloc(0x400u);
                  if ( v7 )
                  {
                    while ( !MakeSelfRelativeSD(v9, v7, &cbSecurityDescriptor) )
                    {
                      if ( GetLastError() != 122 )
                        goto LABEL_39;
                      v26 = PkiRealloc(v7, cbSecurityDescriptor);
                      if ( !v26 )
                        goto LABEL_39;
                      v7 = (void *)v26;
                    }
                    LastError = RegSetKeySecurity(hKeya, 0x80000004, v7);
                    if ( !LastError )
                    {
                      v12 = 1;
                      goto LABEL_36;
                    }
LABEL_34:
                    v27 = LastError;
LABEL_38:
                    SetLastError(v27);
                  }
                }
              }
            }
          }
        }
LABEL_39:
        LastError = GetLastError();
        v12 = 0;
LABEL_36:
        v6 = v29;
        goto LABEL_43;
      }
LABEL_40:
      v6 = v29;
    }
    else
    {
      v6 = 0;
    }
  }
LABEL_42:
  LastError = GetLastError();
  v12 = 0;
  if ( v13 )
  {
LABEL_43:
    if ( BindingHandle )
      RpcRevertToSelf();
    else
      RevertToSelf();
  }
  v4 = a3;
LABEL_47:
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  PkiDefaultCryptFree(v7);
  PkiDefaultCryptFree(v9);
  PkiDefaultCryptFree(v6);
  PkiDefaultCryptFree(v8);
  if ( !v12 )
    SetLastError(LastError);
  result = v12;
  *v4 = dwDisposition == 1;
  return result;
}

```

## disassembly

```asm
0x1800e0d10  mov     rax, rsp
0x1800e0d13  mov     [rax+10h], rbx
0x1800e0d17  mov     [rax+18h], r8
0x1800e0d1b  mov     [rax+8], rcx
0x1800e0d1f  push    rbp
0x1800e0d20  push    rsi
0x1800e0d21  push    rdi
0x1800e0d22  push    r12
0x1800e0d24  push    r13
0x1800e0d26  push    r14
0x1800e0d28  push    r15
0x1800e0d2a  lea     rbp, [rax-5Fh]
0x1800e0d2e  sub     rsp, 0A0h
0x1800e0d35  xor     eax, eax
0x1800e0d37  mov     [rbp+57h+dwDisposition], 2
0x1800e0d3e  mov     rbx, rdx
0x1800e0d41  mov     [rbp+57h+hKey], rax
0x1800e0d45  mov     r13, r8
0x1800e0d48  mov     [rbp+57h+TokenHandle], rax
0x1800e0d4c  mov     rdi, rcx
0x1800e0d4f  mov     [rbp+57h+cbSecurityDescriptor], eax
0x1800e0d52  mov     rcx, rbx; hKey
0x1800e0d55  mov     [rbp+57h+pAce], rax
0x1800e0d59  xor     r9d, r9d; Reserved
0x1800e0d5c  mov     [rbp+57h+dwDaclSize], eax
0x1800e0d5f  xor     r8d, r8d; samDesired
0x1800e0d62  mov     [rbp+57h+dwSaclSize], eax
0x1800e0d65  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\SystemCertificates"...
0x1800e0d6c  mov     [rbp+57h+dwOwnerSize], eax
0x1800e0d6f  mov     r12d, eax
0x1800e0d72  mov     [rbp+57h+dwPrimaryGroupSize], eax
0x1800e0d75  mov     esi, eax
0x1800e0d77  mov     r14d, eax
0x1800e0d7a  mov     r15d, eax
0x1800e0d7d  call    cs:__imp_RegDeleteKeyExW
0x1800e0d83  test    rdi, rdi
0x1800e0d86  jz      short loc_1800E0DAC
0x1800e0d88  mov     rcx, rdi; BindingHandle
0x1800e0d8b  call    cs:__imp_RpcImpersonateClient
0x1800e0d91  test    eax, eax
0x1800e0d93  jz      short loc_1800E0DC1
0x1800e0d95  mov     ecx, eax; dwErrCode
0x1800e0d97  call    cs:__imp_SetLastError
0x1800e0d9d  call    cs:__imp_GetLastError
0x1800e0da3  mov     ebx, eax
0x1800e0da5  xor     edi, edi
0x1800e0da7  jmp     loc_1800E1164
0x1800e0dac  xor     r13d, r13d
0x1800e0daf  lea     ecx, [r13+2]; ImpersonationLevel
0x1800e0db3  call    cs:__imp_ImpersonateSelf
0x1800e0db9  test    eax, eax
0x1800e0dbb  jz      loc_1800E113C
0x1800e0dc1  lea     rax, [rbp+57h+dwDisposition]
0x1800e0dc5  xor     r9d, r9d; lpClass
0x1800e0dc8  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x1800e0dcd  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\SystemCertificates"...
0x1800e0dd4  lea     rax, [rbp+57h+hKey]
0x1800e0dd8  xor     r8d, r8d; Reserved
0x1800e0ddb  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800e0de0  mov     rcx, rbx; hKey
0x1800e0de3  mov     [rsp+0D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800e0de8  mov     [rsp+0D0h+samDesired], 60000h; samDesired
0x1800e0df0  mov     [rsp+0D0h+dwOptions], esi; dwOptions
0x1800e0df4  call    cs:__imp_RegCreateKeyExW
0x1800e0dfa  test    eax, eax
0x1800e0dfc  jz      short loc_1800E0E15
0x1800e0dfe  mov     ecx, eax; dwErrCode
0x1800e0e00  call    cs:__imp_SetLastError
0x1800e0e06  call    cs:__imp_GetLastError
0x1800e0e0c  mov     ebx, eax
0x1800e0e0e  xor     edi, edi
0x1800e0e10  jmp     loc_1800E114B
0x1800e0e15  mov     ebx, 1
0x1800e0e1a  mov     r13d, ebx
0x1800e0e1d  call    cs:__imp_GetCurrentThread
0x1800e0e23  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800e0e27  mov     r8d, ebx; OpenAsSelf
0x1800e0e2a  mov     rcx, rax; ThreadHandle
0x1800e0e2d  lea     edx, [rbx+7]; DesiredAccess
0x1800e0e30  call    cs:__imp_OpenThreadToken
0x1800e0e36  test    eax, eax
0x1800e0e38  jz      loc_1800E113C
0x1800e0e3e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800e0e42  mov     edx, ebx; TokenInformationClass
0x1800e0e44  call    AllocAndGetTokenInfo
0x1800e0e49  mov     [rbp+57h+var_70], rax
0x1800e0e4d  test    rax, rax
0x1800e0e50  jz      loc_1800E1139
0x1800e0e56  mov     r12, [rax]
0x1800e0e59  mov     rcx, r12; pSid
0x1800e0e5c  call    cs:__imp_GetLengthSid
0x1800e0e62  mov     rcx, cs:pSid; pSid
0x1800e0e69  mov     ebx, eax
0x1800e0e6b  call    cs:__imp_GetLengthSid
0x1800e0e71  mov     rcx, cs:Sid; pSid
0x1800e0e78  add     ebx, eax
0x1800e0e7a  call    cs:__imp_GetLengthSid
0x1800e0e80  add     eax, 20h ; ' '
0x1800e0e83  add     ebx, eax
0x1800e0e85  mov     ecx, ebx; uBytes
0x1800e0e87  call    PkiNonzeroAlloc
0x1800e0e8c  mov     r14, rax
0x1800e0e8f  test    rax, rax
0x1800e0e92  jz      loc_1800E1127
0x1800e0e98  lea     edi, [r13+1]
0x1800e0e9c  mov     edx, ebx; nAclLength
0x1800e0e9e  mov     r8d, edi; dwAclRevision
0x1800e0ea1  mov     rcx, rax; pAcl
0x1800e0ea4  call    cs:__imp_InitializeAcl
0x1800e0eaa  test    eax, eax
0x1800e0eac  jz      loc_1800E1133
0x1800e0eb2  mov     r9, cs:Sid; pSid
0x1800e0eb9  mov     r8d, 0F003Fh; AccessMask
0x1800e0ebf  mov     edx, edi; dwAceRevision
0x1800e0ec1  mov     rcx, r14; pAcl
0x1800e0ec4  call    cs:__imp_AddAccessAllowedAce
0x1800e0eca  test    eax, eax
0x1800e0ecc  jz      loc_1800E1127
0x1800e0ed2  mov     ebx, 20019h
0x1800e0ed7  mov     r9, r12; pSid
0x1800e0eda  mov     r8d, ebx; AccessMask
0x1800e0edd  mov     edx, edi; dwAceRevision
0x1800e0edf  mov     rcx, r14; pAcl
0x1800e0ee2  call    cs:__imp_AddAccessAllowedAce
0x1800e0ee8  test    eax, eax
0x1800e0eea  jz      loc_1800E1127
0x1800e0ef0  mov     r9, cs:pSid; pSid
0x1800e0ef7  mov     r8d, ebx; AccessMask
0x1800e0efa  mov     edx, edi; dwAceRevision
0x1800e0efc  mov     rcx, r14; pAcl
0x1800e0eff  call    cs:__imp_AddAccessAllowedAce
0x1800e0f05  test    eax, eax
0x1800e0f07  jz      loc_1800E1127
0x1800e0f0d  xor     ebx, ebx
0x1800e0f0f  mov     r12d, r13d
0x1800e0f12  cmp     ebx, 3
0x1800e0f15  jnb     short loc_1800E0F3B
0x1800e0f17  lea     r8, [rbp+57h+pAce]; pAce
0x1800e0f1b  mov     edx, ebx; dwAceIndex
0x1800e0f1d  mov     rcx, r14; pAcl
0x1800e0f20  call    cs:__imp_GetAce
0x1800e0f26  test    eax, eax
0x1800e0f28  jz      loc_1800E1127
0x1800e0f2e  mov     rax, [rbp+57h+pAce]
0x1800e0f32  add     ebx, r12d
0x1800e0f35  mov     [rax+1], dil
0x1800e0f39  jmp     short loc_1800E0F12
0x1800e0f3b  mov     edi, 400h
0x1800e0f40  mov     ecx, edi; uBytes
0x1800e0f42  mov     [rbp+57h+cbSecurityDescriptor], edi
0x1800e0f45  call    PkiZeroAlloc
0x1800e0f4a  mov     rsi, rax
0x1800e0f4d  test    rax, rax
0x1800e0f50  jz      loc_1800E1127
0x1800e0f56  mov     rcx, [rbp+57h+hKey]; hKey
0x1800e0f5a  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800e0f5e  mov     r8, rsi; pSecurityDescriptor
0x1800e0f61  mov     edx, 80000004h; SecurityInformation
0x1800e0f66  call    cs:__imp_RegGetKeySecurity
0x1800e0f6c  mov     ebx, eax
0x1800e0f6e  test    eax, eax
0x1800e0f70  jz      short loc_1800E0F94
0x1800e0f72  cmp     eax, 7Ah ; 'z'
0x1800e0f75  jnz     loc_1800E110F
0x1800e0f7b  mov     edx, [rbp+57h+cbSecurityDescriptor]
0x1800e0f7e  mov     rcx, rsi
0x1800e0f81  call    PkiRealloc
0x1800e0f86  test    rax, rax
0x1800e0f89  jz      loc_1800E1127
0x1800e0f8f  mov     rsi, rax
0x1800e0f92  jmp     short loc_1800E0F56
0x1800e0f94  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x1800e0f98  mov     [rbp+57h+cbSecurityDescriptor], r15d
0x1800e0f9c  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x1800e0fa1  lea     r8, [rbp+57h+cbSecurityDescriptor]; lpdwAbsoluteSecurityDescriptorSize
0x1800e0fa5  mov     [rsp+0D0h+pPrimaryGroup], r15; pPrimaryGroup
0x1800e0faa  lea     rax, [rbp+57h+dwOwnerSize]
0x1800e0fae  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwOwnerSize
0x1800e0fb3  xor     r9d, r9d; pDacl
0x1800e0fb6  mov     [rsp+0D0h+phkResult], r15; pOwner
0x1800e0fbb  lea     rax, [rbp+57h+dwSaclSize]
0x1800e0fbf  mov     [rsp+0D0h+lpSecurityAttributes], rax; lpdwSaclSize
0x1800e0fc4  xor     edx, edx; pAbsoluteSecurityDescriptor
0x1800e0fc6  lea     rax, [rbp+57h+dwDaclSize]
0x1800e0fca  mov     qword ptr [rsp+0D0h+samDesired], r15; pSacl
0x1800e0fcf  mov     rcx, rsi; pSelfRelativeSecurityDescriptor
0x1800e0fd2  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpdwDaclSize
0x1800e0fd7  call    cs:__imp_MakeAbsoluteSD
0x1800e0fdd  test    eax, eax
0x1800e0fdf  jnz     loc_1800E111C
0x1800e0fe5  call    cs:__imp_GetLastError
0x1800e0feb  cmp     eax, 7Ah ; 'z'
0x1800e0fee  jnz     loc_1800E1127
0x1800e0ff4  mov     ecx, [rbp+57h+dwOwnerSize]
0x1800e0ff7  add     ecx, [rbp+57h+dwPrimaryGroupSize]
0x1800e0ffa  add     ecx, [rbp+57h+dwSaclSize]
0x1800e0ffd  add     ecx, [rbp+57h+dwDaclSize]
0x1800e1000  add     ecx, [rbp+57h+cbSecurityDescriptor]; uBytes
0x1800e1003  call    PkiZeroAlloc
0x1800e1008  mov     r15, rax
0x1800e100b  test    rax, rax
0x1800e100e  jz      loc_1800E1127
0x1800e1014  mov     r8d, [rbp+57h+dwDaclSize]
0x1800e1018  mov     r9d, [rbp+57h+cbSecurityDescriptor]
0x1800e101c  mov     ecx, [rbp+57h+dwSaclSize]
0x1800e101f  mov     r10d, [rbp+57h+dwOwnerSize]
0x1800e1023  add     r10, rcx
0x1800e1026  add     r10, r8
0x1800e1029  lea     rdx, [rcx+r8]
0x1800e102d  add     r10, r9
0x1800e1030  add     r10, rax
0x1800e1033  lea     rcx, [rbp+57h+dwPrimaryGroupSize]
0x1800e1037  mov     [rsp+50h], rcx; lpdwPrimaryGroupSize
0x1800e103c  add     rdx, r9
0x1800e103f  mov     [rsp+0D0h+pPrimaryGroup], r10; pPrimaryGroup
0x1800e1044  lea     rcx, [rbp+57h+dwOwnerSize]
0x1800e1048  mov     [rsp+0D0h+lpdwDisposition], rcx; lpdwOwnerSize
0x1800e104d  add     rdx, rax
0x1800e1050  mov     [rsp+0D0h+phkResult], rdx; pOwner
0x1800e1055  lea     rax, [r8+r9]
0x1800e1059  add     rax, r15
0x1800e105c  lea     rcx, [rbp+57h+dwSaclSize]
0x1800e1060  mov     [rsp+0D0h+lpSecurityAttributes], rcx; lpdwSaclSize
0x1800e1065  lea     r8, [rbp+57h+cbSecurityDescriptor]; lpdwAbsoluteSecurityDescriptorSize
0x1800e1069  mov     qword ptr [rsp+0D0h+samDesired], rax; pSacl
0x1800e106e  add     r9, r15; pDacl
0x1800e1071  lea     rax, [rbp+57h+dwDaclSize]
0x1800e1075  mov     rdx, r15; pAbsoluteSecurityDescriptor
0x1800e1078  mov     rcx, rsi; pSelfRelativeSecurityDescriptor
0x1800e107b  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpdwDaclSize
0x1800e1080  call    cs:__imp_MakeAbsoluteSD
0x1800e1086  test    eax, eax
0x1800e1088  jz      loc_1800E1127
0x1800e108e  xor     r9d, r9d; bDaclDefaulted
0x1800e1091  mov     r8, r14; pDacl
0x1800e1094  mov     edx, r12d; bDaclPresent
0x1800e1097  mov     rcx, r15; pSecurityDescriptor
0x1800e109a  call    cs:__imp_SetSecurityDescriptorDacl
0x1800e10a0  test    eax, eax
0x1800e10a2  jz      loc_1800E1133
0x1800e10a8  mov     rcx, rsi; hMem
0x1800e10ab  call    PkiDefaultCryptFree
0x1800e10b0  mov     rcx, rdi; uBytes
0x1800e10b3  mov     [rbp+57h+cbSecurityDescriptor], edi
0x1800e10b6  call    PkiZeroAlloc
0x1800e10bb  mov     rsi, rax
0x1800e10be  test    rax, rax
0x1800e10c1  jz      short loc_1800E1127
0x1800e10c3  lea     r8, [rbp+57h+cbSecurityDescriptor]; lpdwBufferLength
0x1800e10c7  mov     rdx, rsi; pSelfRelativeSecurityDescriptor
0x1800e10ca  mov     rcx, r15; pAbsoluteSecurityDescriptor
0x1800e10cd  call    cs:__imp_MakeSelfRelativeSD
0x1800e10d3  test    eax, eax
0x1800e10d5  jnz     short loc_1800E10F7
0x1800e10d7  call    cs:__imp_GetLastError
0x1800e10dd  cmp     eax, 7Ah ; 'z'
0x1800e10e0  jnz     short loc_1800E1127
0x1800e10e2  mov     edx, [rbp+57h+cbSecurityDescriptor]
0x1800e10e5  mov     rcx, rsi
0x1800e10e8  call    PkiRealloc
0x1800e10ed  test    rax, rax
0x1800e10f0  jz      short loc_1800E1127
0x1800e10f2  mov     rsi, rax
0x1800e10f5  jmp     short loc_1800E10C3
0x1800e10f7  mov     rcx, [rbp+57h+hKey]; hKey
0x1800e10fb  mov     r8, rsi; pSecurityDescriptor
0x1800e10fe  mov     edx, 80000004h; SecurityInformation
0x1800e1103  call    cs:__imp_RegSetKeySecurity
0x1800e1109  mov     ebx, eax
0x1800e110b  test    eax, eax
0x1800e110d  jz      short loc_1800E1113
0x1800e110f  mov     ecx, ebx
0x1800e1111  jmp     short loc_1800E1121
0x1800e1113  mov     edi, r12d
0x1800e1116  mov     r12, [rbp+57h+var_70]
0x1800e111a  jmp     short loc_1800E114B
0x1800e111c  mov     ecx, 54Fh; dwErrCode
0x1800e1121  call    cs:__imp_SetLastError
0x1800e1127  call    cs:__imp_GetLastError
0x1800e112d  mov     ebx, eax
0x1800e112f  xor     edi, edi
0x1800e1131  jmp     short loc_1800E1116
0x1800e1133  mov     r12, [rbp+57h+var_70]
0x1800e1137  jmp     short loc_1800E113C
0x1800e1139  mov     r12, rax
0x1800e113c  call    cs:__imp_GetLastError
0x1800e1142  mov     ebx, eax
0x1800e1144  xor     edi, edi
0x1800e1146  test    r13d, r13d
0x1800e1149  jz      short loc_1800E1160
0x1800e114b  cmp     [rbp+57h+arg_0], 0
0x1800e1150  jz      short loc_1800E115A
0x1800e1152  call    cs:__imp_RpcRevertToSelf
0x1800e1158  jmp     short loc_1800E1160
0x1800e115a  call    cs:__imp_RevertToSelf
0x1800e1160  mov     r13, [rbp+57h+arg_10]
0x1800e1164  mov     rcx, [rbp+57h+hKey]; hKey
0x1800e1168  test    rcx, rcx
0x1800e116b  jz      short loc_1800E1173
0x1800e116d  call    cs:__imp_RegCloseKey
  ... truncated ...
```
