# HNS::Service::Server::ComHNSApi::CheckCallerAccess(void)

- ea: `0x180198ca0`
- end: `0x180198f59`
- name: `?CheckCallerAccess@ComHNSApi@Server@Service@HNS@@QEAAJXZ`
- size: `697`
- prototype: `__int64 __fastcall(HNS::Service::Server::ComHNSApi *__hidden this)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180198a40`
- `0x180198b70`
- `0x180198ff0`
- `0x180199120`
- `0x180199430`
- `0x180199590`

## callees

- `0x18005f0c0`
- `0x18007dd40`
- `0x180198ca0`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180198d37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180198e5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180198d37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180198e5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180198d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180198e97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180198d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180198e97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180198e79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180198e79`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180198e8d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180198e8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198f1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198f1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180198e4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180198e4b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180198d5b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180198d5b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180198e69`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180198e69`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180198f24`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180198f24`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x180198e13`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x180198e13`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180198d8d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180198d8d`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180198eed`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180198eed`

## string_xrefs

- `0x180198d69`: `Failed in memory allocation for security descriptors.`
- `0x180198e2f`: `Failed to build security descriptors.`
- `0x180198efd`: `Access check failed, caller doesn't have required access.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HNS::Service::Server::ComHNSApi::CheckCallerAccess(HNS::Service::Server::ComHNSApi *this)
{
  PSECURITY_DESCRIPTOR *pNewSD; // r14
  WCHAR *v2; // rax
  WCHAR *v3; // rdi
  int v4; // ebx
  signed int v5; // eax
  signed int v6; // eax
  unsigned int v7; // ecx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v10; // eax
  DWORD cbSid; // [rsp+50h] [rbp-49h] BYREF
  WINBOOL AccessStatus; // [rsp+54h] [rbp-45h] BYREF
  DWORD GrantedAccess; // [rsp+58h] [rbp-41h] BYREF
  DWORD PrivilegeSetLength; // [rsp+5Ch] [rbp-3Dh] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-39h] BYREF
  PSRWLOCK SRWLock; // [rsp+68h] [rbp-31h] BYREF
  _EXPLICIT_ACCESS_W pListOfAccessEntries; // [rsp+70h] [rbp-29h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+A0h] [rbp+7h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+B0h] [rbp+17h] BYREF

  TokenHandle = (void *)-1LL;
  GrantedAccess = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  PrivilegeSetLength = 20;
  GenericMapping = 0;
  AccessStatus = 0;
  pNewSD = (PSECURITY_DESCRIPTOR *)((char *)this + 136);
  if ( *((_QWORD *)this + 17) )
  {
LABEL_22:
    v4 = CoImpersonateClient();
    if ( v4 >= 0 )
    {
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle)
        && (GenericMapping.GenericAll = 1,
            GenericMapping.GenericExecute = 1,
            GenericMapping.GenericRead = 1,
            GenericMapping.GenericWrite = 1,
            AccessCheck(
              *pNewSD,
              TokenHandle,
              1u,
              &GenericMapping,
              &PrivilegeSet,
              &PrivilegeSetLength,
              &GrantedAccess,
              &AccessStatus)) )
      {
        if ( AccessStatus != 1 )
        {
          v4 = -2147024891;
          LogError(-2147024891, L"Access check failed, caller doesn't have required access.");
        }
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    goto LABEL_29;
  }
  (*(void (__fastcall **)(char *, PSRWLOCK *))(*((_QWORD *)this + 2) + 8LL))((char *)this + 16, &SRWLock);
  if ( *pNewSD )
  {
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    goto LABEL_22;
  }
  memset(&pListOfAccessEntries, 0, sizeof(pListOfAccessEntries));
  cbSid = 68;
  v2 = (WCHAR *)LocalAlloc(0, 0x44u);
  v3 = v2;
  if ( !v2 )
  {
    v4 = -2147024882;
    LogError(-2147024882, L"Failed in memory allocation for security descriptors.");
    goto LABEL_19;
  }
  if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v2, &cbSid) )
  {
    pListOfAccessEntries.grfAccessPermissions = 2031617;
    *(_QWORD *)&pListOfAccessEntries.grfAccessMode = 1;
    *(_QWORD *)&pListOfAccessEntries.Trustee.MultipleTrusteeOperation = 0;
    pListOfAccessEntries.Trustee.pMultipleTrustee = 0;
    pListOfAccessEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
    pListOfAccessEntries.Trustee.ptstrName = v3;
    v6 = BuildSecurityDescriptorW(
           &pListOfAccessEntries.Trustee,
           &pListOfAccessEntries.Trustee,
           1u,
           &pListOfAccessEntries,
           0,
           0,
           0,
           &cbSid,
           pNewSD);
    v4 = v6;
    if ( !v6 )
    {
      v4 = 0;
      goto LABEL_18;
    }
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    else
      v7 = v6;
    LogError(v7, L"Failed to build security descriptors.");
    if ( v4 <= 0 )
      goto LABEL_18;
    v4 = (unsigned __int16)v4;
    goto LABEL_10;
  }
  v5 = GetLastError();
  v4 = v5;
  if ( v5 > 0 )
  {
    v4 = (unsigned __int16)v5;
LABEL_10:
    v4 |= 0x80070000;
  }
LABEL_18:
  LocalFree(v3);
LABEL_19:
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v4 >= 0 )
    goto LABEL_22;
LABEL_29:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  v10 = CoRevertToSelf();
  if ( v4 >= 0 )
    return v10;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180198ca0  mov     [rsp-8+arg_8], rbx
0x180198ca5  mov     [rsp-8+arg_10], rsi
0x180198caa  push    rbp
0x180198cab  push    rdi
0x180198cac  push    r12
0x180198cae  push    r13
0x180198cb0  push    r14
0x180198cb2  lea     rbp, [rsp-37h]
0x180198cb7  sub     rsp, 0D0h
0x180198cbe  mov     rax, cs:__security_cookie
0x180198cc5  xor     rax, rsp
0x180198cc8  mov     [rbp+57h+var_28], rax
0x180198ccc  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180198cd4  mov     [rbp+57h+GrantedAccess], 0
0x180198cdb  xorps   xmm0, xmm0
0x180198cde  xor     eax, eax
0x180198ce0  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x180198ce4  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x180198ce7  mov     [rbp+57h+PrivilegeSetLength], 14h
0x180198cee  movups  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x180198cf2  mov     [rbp+57h+AccessStatus], eax
0x180198cf5  lea     r14, [rcx+88h]
0x180198cfc  mov     r12d, 80070000h
0x180198d02  lea     r13d, [rax+1]
0x180198d06  cmp     [r14], rax
0x180198d09  jnz     loc_180198E69
0x180198d0f  add     rcx, 10h
0x180198d13  mov     rax, [rcx]
0x180198d16  lea     rdx, [rbp+57h+SRWLock]
0x180198d1a  mov     rax, [rax+8]
0x180198d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198d23  nop
0x180198d24  cmp     qword ptr [r14], 0
0x180198d28  jz      short loc_180198D42
0x180198d2a  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180198d2e  test    rcx, rcx
0x180198d31  jz      loc_180198E69
0x180198d37  call    cs:__imp_ReleaseSRWLockExclusive
0x180198d3d  jmp     loc_180198E69
0x180198d42  xorps   xmm0, xmm0
0x180198d45  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.grfAccessPermissions], xmm0
0x180198d49  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.Trustee.pMultipleTrustee], xmm0
0x180198d4d  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.Trustee.TrusteeType], xmm0
0x180198d51  mov     edx, 44h ; 'D'; uBytes
0x180198d56  mov     [rbp+57h+cbSid], edx
0x180198d59  xor     ecx, ecx; uFlags
0x180198d5b  call    cs:__imp_LocalAlloc
0x180198d61  mov     rdi, rax
0x180198d64  test    rax, rax
0x180198d67  jnz     short loc_180198D81
0x180198d69  lea     rdx, aFailedInMemory; "Failed in memory allocation for securit"...
0x180198d70  mov     ebx, 8007000Eh
0x180198d75  mov     ecx, ebx; int
0x180198d77  call    ?LogError@@YAXJPEBGZZ; LogError(long,ushort const *,...)
0x180198d7c  jmp     loc_180198E52
0x180198d81  lea     r9, [rbp+57h+cbSid]; cbSid
0x180198d85  mov     r8, rdi; pSid
0x180198d88  xor     edx, edx; DomainSid
0x180198d8a  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180198d8d  call    cs:__imp_CreateWellKnownSid
0x180198d93  test    eax, eax
0x180198d95  jnz     short loc_180198DB2
0x180198d97  call    cs:__imp_GetLastError
0x180198d9d  mov     ebx, eax
0x180198d9f  test    eax, eax
0x180198da1  jle     loc_180198E48
0x180198da7  movzx   ebx, ax
0x180198daa  or      ebx, r12d
0x180198dad  jmp     loc_180198E48
0x180198db2  mov     [rbp+57h+pListOfAccessEntries.grfAccessPermissions], 1F0001h
0x180198db9  mov     qword ptr [rbp+57h+pListOfAccessEntries.grfAccessMode], 1
0x180198dc1  mov     qword ptr [rbp+57h+pListOfAccessEntries.Trustee.MultipleTrusteeOperation], 0
0x180198dc9  mov     [rbp+57h+pListOfAccessEntries.Trustee.pMultipleTrustee], 0
0x180198dd1  mov     [rbp+57h+pListOfAccessEntries.Trustee.TrusteeType], 2
0x180198dd8  mov     [rbp+57h+pListOfAccessEntries.Trustee.ptstrName], rdi
0x180198ddc  mov     [rsp+0F0h+pNewSD], r14; pNewSD
0x180198de1  lea     rax, [rbp+57h+cbSid]
0x180198de5  mov     [rsp+0F0h+pSizeNewSD], rax; pSizeNewSD
0x180198dea  mov     [rsp+0F0h+pOldSD], 0; pOldSD
0x180198df3  mov     [rsp+0F0h+pListOfAuditEntries], 0; pListOfAuditEntries
0x180198dfc  mov     [rsp+0F0h+cCountOfAuditEntries], 0; cCountOfAuditEntries
0x180198e04  lea     r9, [rbp+57h+pListOfAccessEntries]; pListOfAccessEntries
0x180198e08  mov     r8d, r13d; cCountOfAccessEntries
0x180198e0b  lea     rdx, [rbp+57h+pListOfAccessEntries.Trustee]; pGroup
0x180198e0f  lea     rcx, [rbp+57h+pListOfAccessEntries.Trustee]; pOwner
0x180198e13  call    cs:__imp_BuildSecurityDescriptorW
0x180198e19  mov     ebx, eax
0x180198e1b  test    eax, eax
0x180198e1d  jz      short loc_180198E46
0x180198e1f  movzx   esi, bx
0x180198e22  test    eax, eax
0x180198e24  jg      short loc_180198E2A
0x180198e26  mov     ecx, eax
0x180198e28  jmp     short loc_180198E2F
0x180198e2a  mov     ecx, esi
0x180198e2c  or      ecx, r12d; int
0x180198e2f  lea     rdx, aFailedToBuildS; "Failed to build security descriptors."
0x180198e36  call    ?LogError@@YAXJPEBGZZ; LogError(long,ushort const *,...)
0x180198e3b  test    ebx, ebx
0x180198e3d  jle     short loc_180198E48
0x180198e3f  mov     ebx, esi
0x180198e41  jmp     loc_180198DAA
0x180198e46  xor     ebx, ebx
0x180198e48  mov     rcx, rdi; hMem
0x180198e4b  call    cs:__imp_LocalFree
0x180198e51  nop
0x180198e52  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180198e56  test    rcx, rcx
0x180198e59  jz      short loc_180198E61
0x180198e5b  call    cs:__imp_ReleaseSRWLockExclusive
0x180198e61  test    ebx, ebx
0x180198e63  js      loc_180198F10
0x180198e69  call    cs:__imp_CoImpersonateClient
0x180198e6f  mov     ebx, eax
0x180198e71  test    eax, eax
0x180198e73  js      loc_180198F10
0x180198e79  call    cs:__imp_GetCurrentThread
0x180198e7f  mov     rcx, rax; ThreadHandle
0x180198e82  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180198e86  xor     r8d, r8d; OpenAsSelf
0x180198e89  lea     edx, [r8+8]; DesiredAccess
0x180198e8d  call    cs:__imp_OpenThreadToken
0x180198e93  test    eax, eax
0x180198e95  jnz     short loc_180198EAB
0x180198e97  call    cs:__imp_GetLastError
0x180198e9d  mov     ebx, eax
0x180198e9f  test    eax, eax
0x180198ea1  jle     short loc_180198F10
0x180198ea3  movzx   ebx, ax
0x180198ea6  or      ebx, r12d
0x180198ea9  jmp     short loc_180198F10
0x180198eab  mov     [rbp+57h+GenericMapping.GenericAll], r13d
0x180198eaf  mov     [rbp+57h+GenericMapping.GenericExecute], r13d
0x180198eb3  mov     [rbp+57h+GenericMapping.GenericRead], r13d
0x180198eb7  mov     [rbp+57h+GenericMapping.GenericWrite], r13d
0x180198ebb  lea     rax, [rbp+57h+AccessStatus]
0x180198ebf  mov     [rsp+0F0h+pSizeNewSD], rax; AccessStatus
0x180198ec4  lea     rax, [rbp+57h+GrantedAccess]
0x180198ec8  mov     [rsp+0F0h+pOldSD], rax; GrantedAccess
0x180198ecd  lea     rax, [rbp+57h+PrivilegeSetLength]
0x180198ed1  mov     [rsp+0F0h+pListOfAuditEntries], rax; PrivilegeSetLength
0x180198ed6  lea     rax, [rbp+57h+PrivilegeSet]
0x180198eda  mov     qword ptr [rsp+0F0h+cCountOfAuditEntries], rax; PrivilegeSet
0x180198edf  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x180198ee3  mov     r8d, r13d; DesiredAccess
0x180198ee6  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x180198eea  mov     rcx, [r14]; pSecurityDescriptor
0x180198eed  call    cs:__imp_AccessCheck
0x180198ef3  test    eax, eax
0x180198ef5  jz      short loc_180198E97
0x180198ef7  cmp     [rbp+57h+AccessStatus], r13d
0x180198efb  jz      short loc_180198F10
0x180198efd  lea     rdx, aAccessCheckFai; "Access check failed, caller doesn't hav"...
0x180198f04  mov     ebx, 80070005h
0x180198f09  mov     ecx, ebx; int
0x180198f0b  call    ?LogError@@YAXJPEBGZZ; LogError(long,ushort const *,...)
0x180198f10  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180198f14  lea     rdx, [rcx-1]
0x180198f18  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180198f1c  ja      short loc_180198F24
0x180198f1e  call    cs:__imp_CloseHandle
0x180198f24  call    cs:__imp_CoRevertToSelf
0x180198f2a  test    ebx, ebx
0x180198f2c  cmovns  ebx, eax
0x180198f2f  mov     eax, ebx
0x180198f31  mov     rcx, [rbp+57h+var_28]
0x180198f35  xor     rcx, rsp; StackCookie
0x180198f38  call    __security_check_cookie
0x180198f3d  lea     r11, [rsp+0F0h+var_20]
0x180198f45  mov     rbx, [r11+38h]
0x180198f49  mov     rsi, [r11+40h]
0x180198f4d  mov     rsp, r11
0x180198f50  pop     r14
0x180198f52  pop     r13
0x180198f54  pop     r12
0x180198f56  pop     rdi
0x180198f57  pop     rbp
0x180198f58  retn
```
