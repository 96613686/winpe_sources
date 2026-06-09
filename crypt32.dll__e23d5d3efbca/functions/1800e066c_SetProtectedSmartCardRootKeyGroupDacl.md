# SetProtectedSmartCardRootKeyGroupDacl

- ea: `0x1800e066c`
- end: `0x1800e0869`
- name: `SetProtectedSmartCardRootKeyGroupDacl`
- size: `509`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800dfbd4`

## callees

- `0x180028d60`
- `0x180030e60`
- `0x1800599a8`
- `0x1800df150`
- `0x1800e066c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0829`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e081a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e083d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e081a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e083d`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1800e080e`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1800e080e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800e06d4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800e06d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e06c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e06c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e0835`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e0835`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800e07d6`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800e07d6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800e0719`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800e0728`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800e0737`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800e0719`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800e0728`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800e0737`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800e075e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800e075e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800e077f`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800e07a2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800e07bc`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800e077f`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800e07a2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800e07bc`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800e07f8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800e07f8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800e0704`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800e0704`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800e06b6`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800e06b6`

## pseudocode

```c
__int64 __fastcall SetProtectedSmartCardRootKeyGroupDacl(HKEY hKey)
{
  PSID *v2; // r14
  struct _ACL *v3; // rdi
  unsigned int v4; // esi
  HANDLE CurrentProcess; // rax
  PSID *TokenInfo; // rax
  DWORD LengthSid; // ebx
  DWORD v8; // ebx
  DWORD v9; // ebx
  struct _ACL *v10; // rax
  DWORD i; // ebx
  LSTATUS v12; // eax
  DWORD LastError; // ebx
  _OWORD pSecurityDescriptor[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v16; // [rsp+40h] [rbp-10h]
  void *TokenHandle; // [rsp+88h] [rbp+38h] BYREF
  LPVOID pAce; // [rsp+90h] [rbp+40h] BYREF

  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v16 = 0;
  TokenHandle = 0;
  v2 = 0;
  pAce = 0;
  v3 = 0;
  if ( (unsigned int)GetPredefinedSids(hKey) )
  {
    v4 = 1;
    if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      {
        TokenInfo = (PSID *)AllocAndGetTokenInfo(TokenHandle, TokenPrimaryGroup);
        v2 = TokenInfo;
        if ( TokenInfo )
        {
          if ( SetSecurityDescriptorGroup(pSecurityDescriptor, *TokenInfo, 0) )
          {
            LengthSid = GetLengthSid(pSid);
            v8 = GetLengthSid(qword_18015D628) + LengthSid;
            v9 = GetLengthSid(pSid1) + 32 + v8;
            v10 = (struct _ACL *)PkiNonzeroAlloc(v9);
            v3 = v10;
            if ( v10 )
            {
              if ( InitializeAcl(v10, v9, 2u)
                && AddAccessAllowedAce(v3, 2u, 0xF003Fu, pSid1)
                && AddAccessAllowedAce(v3, 2u, 0x20019u, qword_18015D628)
                && AddAccessAllowedAce(v3, 2u, 0x20019u, pSid) )
              {
                for ( i = 0; i < 3; ++i )
                {
                  if ( !GetAce(v3, i, &pAce) )
                    goto LABEL_18;
                  *((_BYTE *)pAce + 1) = 2;
                }
                if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v3, 0) )
                {
                  v12 = RegSetKeySecurity(hKey, 6u, pSecurityDescriptor);
                  if ( !v12 )
                    goto LABEL_19;
                  SetLastError(v12);
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_18:
  v4 = 0;
LABEL_19:
  if ( TokenHandle )
  {
    LastError = GetLastError();
    CloseHandle(TokenHandle);
    SetLastError(LastError);
  }
  PkiDefaultCryptFree(v2);
  PkiDefaultCryptFree(v3);
  return v4;
}

```

## disassembly

```asm
0x1800e066c  mov     [rsp-28h+arg_0], rbx
0x1800e0671  push    rbp
0x1800e0672  push    rsi
0x1800e0673  push    rdi
0x1800e0674  push    r14
0x1800e0676  push    r15
0x1800e0678  mov     rbp, rsp
0x1800e067b  sub     rsp, 50h
0x1800e067f  xor     eax, eax
0x1800e0681  xorps   xmm0, xmm0
0x1800e0684  movups  [rbp+pSecurityDescriptor], xmm0
0x1800e0688  mov     [rbp+var_10], rax
0x1800e068c  mov     r15, rcx
0x1800e068f  movups  [rbp+var_20], xmm0
0x1800e0693  mov     [rbp+TokenHandle], rax
0x1800e0697  xor     r14d, r14d
0x1800e069a  mov     [rbp+pAce], rax
0x1800e069e  xor     edi, edi
0x1800e06a0  call    GetPredefinedSids
0x1800e06a5  test    eax, eax
0x1800e06a7  jz      loc_1800E0820
0x1800e06ad  lea     esi, [rdi+1]
0x1800e06b0  mov     edx, esi; dwRevision
0x1800e06b2  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x1800e06b6  call    cs:__imp_InitializeSecurityDescriptor
0x1800e06bc  test    eax, eax
0x1800e06be  jz      loc_1800E0820
0x1800e06c4  call    cs:__imp_GetCurrentProcess
0x1800e06ca  mov     rcx, rax; ProcessHandle
0x1800e06cd  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800e06d1  lea     edx, [rdi+8]; DesiredAccess
0x1800e06d4  call    cs:__imp_OpenProcessToken
0x1800e06da  test    eax, eax
0x1800e06dc  jz      loc_1800E0820
0x1800e06e2  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800e06e6  lea     edx, [rdi+5]; TokenInformationClass
0x1800e06e9  call    AllocAndGetTokenInfo
0x1800e06ee  mov     r14, rax
0x1800e06f1  test    rax, rax
0x1800e06f4  jz      loc_1800E0820
0x1800e06fa  mov     rdx, [rax]; pGroup
0x1800e06fd  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x1800e0701  xor     r8d, r8d; bGroupDefaulted
0x1800e0704  call    cs:__imp_SetSecurityDescriptorGroup
0x1800e070a  test    eax, eax
0x1800e070c  jz      loc_1800E0820
0x1800e0712  mov     rcx, cs:pSid; pSid
0x1800e0719  call    cs:__imp_GetLengthSid
0x1800e071f  mov     rcx, cs:qword_18015D628; pSid
0x1800e0726  mov     ebx, eax
0x1800e0728  call    cs:__imp_GetLengthSid
0x1800e072e  mov     rcx, cs:pSid1; pSid
0x1800e0735  add     ebx, eax
0x1800e0737  call    cs:__imp_GetLengthSid
0x1800e073d  add     eax, 20h ; ' '
0x1800e0740  add     ebx, eax
0x1800e0742  mov     ecx, ebx; uBytes
0x1800e0744  call    PkiNonzeroAlloc
0x1800e0749  mov     rdi, rax
0x1800e074c  test    rax, rax
0x1800e074f  jz      loc_1800E0820
0x1800e0755  lea     r8d, [rsi+1]; dwAclRevision
0x1800e0759  mov     edx, ebx; nAclLength
0x1800e075b  mov     rcx, rax; pAcl
0x1800e075e  call    cs:__imp_InitializeAcl
0x1800e0764  test    eax, eax
0x1800e0766  jz      loc_1800E0820
0x1800e076c  mov     r9, cs:pSid1; pSid
0x1800e0773  lea     edx, [rsi+1]; dwAceRevision
0x1800e0776  mov     r8d, 0F003Fh; AccessMask
0x1800e077c  mov     rcx, rdi; pAcl
0x1800e077f  call    cs:__imp_AddAccessAllowedAce
0x1800e0785  test    eax, eax
0x1800e0787  jz      loc_1800E0820
0x1800e078d  mov     r9, cs:qword_18015D628; pSid
0x1800e0794  lea     edx, [rsi+1]; dwAceRevision
0x1800e0797  mov     ebx, 20019h
0x1800e079c  mov     rcx, rdi; pAcl
0x1800e079f  mov     r8d, ebx; AccessMask
0x1800e07a2  call    cs:__imp_AddAccessAllowedAce
0x1800e07a8  test    eax, eax
0x1800e07aa  jz      short loc_1800E0820
0x1800e07ac  mov     r9, cs:pSid; pSid
0x1800e07b3  lea     edx, [rsi+1]; dwAceRevision
0x1800e07b6  mov     r8d, ebx; AccessMask
0x1800e07b9  mov     rcx, rdi; pAcl
0x1800e07bc  call    cs:__imp_AddAccessAllowedAce
0x1800e07c2  test    eax, eax
0x1800e07c4  jz      short loc_1800E0820
0x1800e07c6  xor     ebx, ebx
0x1800e07c8  cmp     ebx, 3
0x1800e07cb  jnb     short loc_1800E07EC
0x1800e07cd  lea     r8, [rbp+pAce]; pAce
0x1800e07d1  mov     edx, ebx; dwAceIndex
0x1800e07d3  mov     rcx, rdi; pAcl
0x1800e07d6  call    cs:__imp_GetAce
0x1800e07dc  test    eax, eax
0x1800e07de  jz      short loc_1800E0820
0x1800e07e0  mov     rax, [rbp+pAce]
0x1800e07e4  add     ebx, esi
0x1800e07e6  mov     byte ptr [rax+1], 2
0x1800e07ea  jmp     short loc_1800E07C8
0x1800e07ec  xor     r9d, r9d; bDaclDefaulted
0x1800e07ef  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x1800e07f3  mov     r8, rdi; pDacl
0x1800e07f6  mov     edx, esi; bDaclPresent
0x1800e07f8  call    cs:__imp_SetSecurityDescriptorDacl
0x1800e07fe  test    eax, eax
0x1800e0800  jz      short loc_1800E0820
0x1800e0802  lea     r8, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x1800e0806  mov     edx, 6; SecurityInformation
0x1800e080b  mov     rcx, r15; hKey
0x1800e080e  call    cs:__imp_RegSetKeySecurity
0x1800e0814  test    eax, eax
0x1800e0816  jz      short loc_1800E0822
0x1800e0818  mov     ecx, eax; dwErrCode
0x1800e081a  call    cs:__imp_SetLastError
0x1800e0820  xor     esi, esi
0x1800e0822  cmp     [rbp+TokenHandle], 0
0x1800e0827  jz      short loc_1800E0843
0x1800e0829  call    cs:__imp_GetLastError
0x1800e082f  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e0833  mov     ebx, eax
0x1800e0835  call    cs:__imp_CloseHandle
0x1800e083b  mov     ecx, ebx; dwErrCode
0x1800e083d  call    cs:__imp_SetLastError
0x1800e0843  mov     rcx, r14; hMem
0x1800e0846  call    PkiDefaultCryptFree
0x1800e084b  mov     rcx, rdi; hMem
0x1800e084e  call    PkiDefaultCryptFree
0x1800e0853  mov     rbx, [rsp+50h+arg_0]
0x1800e085b  mov     eax, esi
0x1800e085d  add     rsp, 50h
0x1800e0861  pop     r15
0x1800e0863  pop     r14
0x1800e0865  pop     rdi
0x1800e0866  pop     rsi
0x1800e0867  pop     rbp
0x1800e0868  retn
```
