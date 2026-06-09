# CPolicyMonitor::InitializeSdFromThreadToken(void * *,_ACL * *)

- ea: `0x180054668`
- end: `0x180054b6e`
- name: `?InitializeSdFromThreadToken@CPolicyMonitor@@CAJPEAPEAXPEAPEAU_ACL@@@Z`
- size: `1286`
- prototype: `__int64 __fastcall(void **, struct _ACL **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004b01c`

## callees

- `0x1800077a0`
- `0x18004e850`
- `0x18004ec20`
- `0x18004ec80`
- `0x180054668`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800549d0`
- `ntdll!RtlNtStatusToDosError` at `0x1800549d0`
- `ntdll!RtlFreeSid` at `0x180054b2b`
- `ntdll!RtlFreeSid` at `0x180054b2b`
- `ntdll!RtlAddAccessAllowedAce` at `0x180054a73`
- `ntdll!RtlAddAccessAllowedAce` at `0x180054a8b`
- `ntdll!RtlAddAccessAllowedAce` at `0x180054aa3`
- `ntdll!RtlAddAccessAllowedAce` at `0x180054a73`
- `ntdll!RtlAddAccessAllowedAce` at `0x180054a8b`
- `ntdll!RtlAddAccessAllowedAce` at `0x180054aa3`
- `ntdll!RtlCreateAcl` at `0x180054a56`
- `ntdll!RtlCreateAcl` at `0x180054a56`
- `ntdll!RtlLengthSid` at `0x1800549ec`
- `ntdll!RtlLengthSid` at `0x1800549fe`
- `ntdll!RtlLengthSid` at `0x180054a10`
- `ntdll!RtlLengthSid` at `0x1800549ec`
- `ntdll!RtlLengthSid` at `0x1800549fe`
- `ntdll!RtlLengthSid` at `0x180054a10`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800549be`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800549be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800547a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800547e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005487c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800548c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005490f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005493d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005496b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054acb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800547a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800547e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005487c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800548c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005490f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005493d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005496b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054acb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180054705`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180054705`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800546e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800546e8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180054740`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180054740`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005472a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005472a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054afc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054afc`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005486c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005486c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180054abb`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180054abb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180054795`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800547d8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800548b1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800548ff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180054795`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800547d8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800548b1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800548ff`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18005492d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18005492d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18005495b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18005495b`

## string_xrefs

- `0x18005475c`: `InitializeSdFromThreadToken: Unable to open thread/process token, status %d`
- `0x180054775`: `InitializeSdFromThreadToken: Unable to open thread token, status %d`
- `0x1800547b8`: `InitializeSdFromThreadToken: Get user info from token for size failed, status %d`
- `0x1800547fb`: `InitializeSdFromThreadToken: Get group info from token for size failed, status %d`
- `0x180054826`: `InitializeSdFromThreadToken: Buffer size too small: %d < %d`
- `0x180054855`: `InitializeSdFromThreadToken: Memory allocation for output buffer failed, status %d`
- `0x180054888`: `InitializeSdFromThreadToken: Initialize SD failed, status %d`
- `0x1800548cd`: `InitializeSdFromThreadToken: Get user info from token failed, status %d`
- `0x18005491b`: `InitializeSdFromThreadToken: Get group info from token failed, status %d`
- `0x180054949`: `InitializeSdFromThreadToken: Set owner on SD failed, status %d`
- `0x180054977`: `InitializeSdFromThreadToken: Set group on SD failed, status %d`
- `0x1800549dc`: `InitializeSdFromThreadToken: Failed to allocate packge SID: %d`
- `0x180054a3d`: `InitializeSdFromThreadToken: Memory allocation for the ACL failed, status %d`
- `0x180054ad7`: `InitializeSdFromThreadToken: Set DACL on SD failed, status %d`

## pseudocode

```c
__int64 __fastcall CPolicyMonitor::InitializeSdFromThreadToken(PSID **a1, struct _ACL **a2)
{
  PSID *v2; // rdi
  struct _ACL *v3; // rsi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  int v8; // ebx
  HANDLE CurrentProcess; // rax
  const char *v10; // rdx
  __int64 v11; // r8
  const struct std::nothrow_t *v12; // rdx
  __int64 v13; // rbx
  unsigned __int64 v14; // rcx
  PSID *v15; // rax
  PSID *v16; // r14
  DWORD v17; // eax
  PSID *v18; // rbx
  int v19; // eax
  ULONG v20; // ebx
  ULONG v21; // ebx
  ULONG v22; // ebx
  struct _ACL *v23; // rax
  DWORD TokenInformationLength; // [rsp+60h] [rbp-29h] BYREF
  DWORD ReturnLength; // [rsp+64h] [rbp-25h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-21h] BYREF
  PSID Sid; // [rsp+70h] [rbp-19h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+78h] [rbp-11h] BYREF
  _DWORD v30[4]; // [rsp+80h] [rbp-9h] BYREF
  _DWORD v31[4]; // [rsp+90h] [rbp+7h] BYREF

  v30[0] = 257;
  TokenHandle = 0;
  v2 = 0;
  TokenInformationLength = 0;
  v3 = 0;
  ReturnLength = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  Sid = 0;
  *a1 = 0;
  v30[1] = 83886080;
  v30[2] = 11;
  v31[0] = 257;
  v31[1] = 83886080;
  v31[2] = 4;
  *(_WORD *)&IdentifierAuthority.Value[4] = 3840;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError != 1008 )
    {
      v10 = "InitializeSdFromThreadToken: Unable to open thread token, status %d";
      goto LABEL_6;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      v10 = "InitializeSdFromThreadToken: Unable to open thread/process token, status %d";
LABEL_5:
      v8 = LastError;
LABEL_6:
      v11 = LastError;
LABEL_7:
      _DbgPrintMessage(8, v10, v11);
      goto LABEL_37;
    }
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError != 122 )
    {
      v10 = "InitializeSdFromThreadToken: Get user info from token for size failed, status %d";
      goto LABEL_6;
    }
  }
  if ( !GetTokenInformation(TokenHandle, TokenPrimaryGroup, 0, 0, &ReturnLength) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError != 122 )
    {
      v10 = "InitializeSdFromThreadToken: Get group info from token for size failed, status %d";
      goto LABEL_6;
    }
  }
  v13 = (TokenInformationLength + 7) & 0xFFFFFFF8;
  v14 = (unsigned int)v13 + ReturnLength + 40;
  if ( (unsigned int)v14 < 0x40 )
  {
    v8 = 122;
    _DbgPrintMessage(8, "InitializeSdFromThreadToken: Buffer size too small: %d < %d", v14, 64);
    goto LABEL_37;
  }
  v15 = (PSID *)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
  v2 = v15;
  if ( !v15 )
  {
    v8 = 8;
    v10 = "InitializeSdFromThreadToken: Memory allocation for output buffer failed, status %d";
    v11 = 8;
    goto LABEL_7;
  }
  if ( !InitializeSecurityDescriptor(v15, 1u) )
  {
    LastError = GetLastError();
    v10 = "InitializeSdFromThreadToken: Initialize SD failed, status %d";
    goto LABEL_5;
  }
  v16 = v2 + 5;
  if ( !GetTokenInformation(TokenHandle, TokenUser, v2 + 5, TokenInformationLength, &TokenInformationLength) )
  {
    v17 = GetLastError();
    v10 = "InitializeSdFromThreadToken: Get user info from token failed, status %d";
LABEL_23:
    v11 = v17;
    v8 = v17;
    goto LABEL_7;
  }
  v18 = (PSID *)((char *)v16 + v13);
  if ( !GetTokenInformation(TokenHandle, TokenPrimaryGroup, v18, ReturnLength, &ReturnLength) )
  {
    v17 = GetLastError();
    v10 = "InitializeSdFromThreadToken: Get group info from token failed, status %d";
    goto LABEL_23;
  }
  if ( !SetSecurityDescriptorOwner(v2, *v16, 0) )
  {
    v17 = GetLastError();
    v10 = "InitializeSdFromThreadToken: Set owner on SD failed, status %d";
    goto LABEL_23;
  }
  if ( !SetSecurityDescriptorGroup(v2, *v18, 0) )
  {
    v17 = GetLastError();
    v10 = "InitializeSdFromThreadToken: Set group on SD failed, status %d";
    goto LABEL_23;
  }
  v19 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &Sid);
  if ( v19 < 0 )
  {
    v17 = RtlNtStatusToDosError(v19);
    v10 = "InitializeSdFromThreadToken: Failed to allocate packge SID: %d";
    goto LABEL_23;
  }
  v20 = RtlLengthSid(Sid);
  v21 = RtlLengthSid(v31) + v20;
  v22 = RtlLengthSid(v30) + 32 + v21;
  v23 = (struct _ACL *)operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v23;
  if ( v23 )
  {
    RtlCreateAcl(v23, v22, 2u);
    RtlAddAccessAllowedAce(v3, 2u, 1u, v30);
    RtlAddAccessAllowedAce(v3, 2u, 1u, v31);
    RtlAddAccessAllowedAce(v3, 2u, 1u, Sid);
    if ( !SetSecurityDescriptorDacl(v2, 1, v3, 0) )
    {
      v17 = GetLastError();
      v10 = "InitializeSdFromThreadToken: Set DACL on SD failed, status %d";
      goto LABEL_23;
    }
    *a1 = v2;
    v8 = 0;
    *a2 = v3;
    v2 = 0;
    v3 = 0;
  }
  else
  {
    v8 = 8;
    _DbgPrintMessage(8, "InitializeSdFromThreadToken: Memory allocation for the ACL failed, status %d", 8);
  }
LABEL_37:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v2 )
    operator delete(v2, v12);
  if ( v3 )
    operator delete(v3, v12);
  if ( Sid )
    RtlFreeSid(Sid);
  if ( v8 > 0 )
    return (unsigned __int16)v8 | 0x80070000;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180054668  mov     [rsp-8+arg_10], rbx
0x18005466d  push    rbp
0x18005466e  push    rsi
0x18005466f  push    rdi
0x180054670  push    r12
0x180054672  push    r13
0x180054674  push    r14
0x180054676  push    r15
0x180054678  lea     rbp, [rsp-27h]
0x18005467d  sub     rsp, 0B0h
0x180054684  mov     rax, cs:__security_cookie
0x18005468b  xor     rax, rsp
0x18005468e  mov     [rbp+57h+var_40], rax
0x180054692  xor     r13d, r13d
0x180054695  mov     [rbp+57h+var_60], 101h
0x18005469c  mov     [rbp+57h+TokenHandle], r13
0x1800546a0  mov     edi, r13d
0x1800546a3  mov     [rbp+57h+TokenInformationLength], r13d
0x1800546a7  mov     esi, r13d
0x1800546aa  mov     [rbp+57h+var_7C], r13d
0x1800546ae  mov     r12, rdx
0x1800546b1  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r13d
0x1800546b5  mov     r15, rcx
0x1800546b8  mov     [rbp+57h+var_70], r13
0x1800546bc  mov     [rcx], r13
0x1800546bf  mov     [rbp+57h+var_5C], 5000000h
0x1800546c6  mov     [rbp+57h+var_58], 0Bh
0x1800546cd  mov     [rbp+57h+var_50], 101h
0x1800546d4  mov     [rbp+57h+var_4C], 5000000h
0x1800546db  mov     [rbp+57h+var_48], 4
0x1800546e2  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 0F00h
0x1800546e8  call    cs:__imp_GetCurrentThread
0x1800546ef  nop     dword ptr [rax+rax+00h]
0x1800546f4  lea     r14d, [r13+8]
0x1800546f8  xor     r8d, r8d; OpenAsSelf
0x1800546fb  mov     rcx, rax; ThreadHandle
0x1800546fe  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180054702  mov     edx, r14d; DesiredAccess
0x180054705  call    cs:__imp_OpenThreadToken
0x18005470c  nop     dword ptr [rax+rax+00h]
0x180054711  test    eax, eax
0x180054713  jnz     short loc_18005477E
0x180054715  call    cs:__imp_GetLastError
0x18005471c  nop     dword ptr [rax+rax+00h]
0x180054721  mov     ebx, eax
0x180054723  cmp     eax, 3F0h
0x180054728  jnz     short loc_180054775
0x18005472a  call    cs:__imp_GetCurrentProcess
0x180054731  nop     dword ptr [rax+rax+00h]
0x180054736  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18005473a  mov     edx, r14d; DesiredAccess
0x18005473d  mov     rcx, rax; ProcessHandle
0x180054740  call    cs:__imp_OpenProcessToken
0x180054747  nop     dword ptr [rax+rax+00h]
0x18005474c  test    eax, eax
0x18005474e  jnz     short loc_18005477E
0x180054750  call    cs:__imp_GetLastError
0x180054757  nop     dword ptr [rax+rax+00h]
0x18005475c  lea     rdx, aInitializesdfr_10; "InitializeSdFromThreadToken: Unable to "...
0x180054763  mov     ebx, eax
0x180054765  mov     r8d, eax
0x180054768  mov     ecx, r14d; int
0x18005476b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180054770  jmp     loc_180054AF3
0x180054775  lea     rdx, aInitializesdfr_9; "InitializeSdFromThreadToken: Unable to "...
0x18005477c  jmp     short loc_180054765
0x18005477e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180054782  lea     rax, [rbp+57h+TokenInformationLength]
0x180054786  xor     r9d, r9d; TokenInformationLength
0x180054789  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18005478e  xor     r8d, r8d; TokenInformation
0x180054791  lea     edx, [r9+1]; TokenInformationClass
0x180054795  call    cs:__imp_GetTokenInformation
0x18005479c  nop     dword ptr [rax+rax+00h]
0x1800547a1  test    eax, eax
0x1800547a3  jnz     short loc_1800547C1
0x1800547a5  call    cs:__imp_GetLastError
0x1800547ac  nop     dword ptr [rax+rax+00h]
0x1800547b1  mov     ebx, eax
0x1800547b3  cmp     eax, 7Ah ; 'z'
0x1800547b6  jz      short loc_1800547C1
0x1800547b8  lea     rdx, aInitializesdfr_5; "InitializeSdFromThreadToken: Get user i"...
0x1800547bf  jmp     short loc_180054765
0x1800547c1  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800547c5  lea     rax, [rbp+57h+var_7C]
0x1800547c9  xor     r9d, r9d; TokenInformationLength
0x1800547cc  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1800547d1  xor     r8d, r8d; TokenInformation
0x1800547d4  lea     edx, [r9+5]; TokenInformationClass
0x1800547d8  call    cs:__imp_GetTokenInformation
0x1800547df  nop     dword ptr [rax+rax+00h]
0x1800547e4  test    eax, eax
0x1800547e6  jnz     short loc_180054807
0x1800547e8  call    cs:__imp_GetLastError
0x1800547ef  nop     dword ptr [rax+rax+00h]
0x1800547f4  mov     ebx, eax
0x1800547f6  cmp     eax, 7Ah ; 'z'
0x1800547f9  jz      short loc_180054807
0x1800547fb  lea     rdx, aInitializesdfr_7; "InitializeSdFromThreadToken: Get group "...
0x180054802  jmp     loc_180054765
0x180054807  mov     ebx, [rbp+57h+TokenInformationLength]
0x18005480a  mov     r9d, 40h ; '@'
0x180054810  mov     ecx, [rbp+57h+var_7C]
0x180054813  add     ebx, 7
0x180054816  and     ebx, 0FFFFFFF8h
0x180054819  add     ecx, 28h ; '('
0x18005481c  add     ecx, ebx; unsigned __int64
0x18005481e  cmp     ecx, r9d
0x180054821  jnb     short loc_18005483E
0x180054823  mov     r8d, ecx
0x180054826  lea     rdx, aInitializesdfr_0; "InitializeSdFromThreadToken: Buffer siz"...
0x18005482d  mov     ecx, r14d; int
0x180054830  lea     ebx, [r9+3Ah]
0x180054834  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180054839  jmp     loc_180054AF3
0x18005483e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180054845  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005484a  mov     rdi, rax
0x18005484d  test    rax, rax
0x180054850  jnz     short loc_180054864
0x180054852  mov     ebx, r14d
0x180054855  lea     rdx, aInitializesdfr_11; "InitializeSdFromThreadToken: Memory all"...
0x18005485c  mov     r8d, r14d
0x18005485f  jmp     loc_180054768
0x180054864  mov     edx, 1; dwRevision
0x180054869  mov     rcx, rdi; pSecurityDescriptor
0x18005486c  call    cs:__imp_InitializeSecurityDescriptor
0x180054873  nop     dword ptr [rax+rax+00h]
0x180054878  test    eax, eax
0x18005487a  jnz     short loc_180054894
0x18005487c  call    cs:__imp_GetLastError
0x180054883  nop     dword ptr [rax+rax+00h]
0x180054888  lea     rdx, aInitializesdfr_1; "InitializeSdFromThreadToken: Initialize"...
0x18005488f  jmp     loc_180054763
0x180054894  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180054898  lea     rax, [rbp+57h+TokenInformationLength]
0x18005489c  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800548a0  lea     r14, [rdi+28h]
0x1800548a4  mov     r8, r14; TokenInformation
0x1800548a7  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1800548ac  mov     edx, 1; TokenInformationClass
0x1800548b1  call    cs:__imp_GetTokenInformation
0x1800548b8  nop     dword ptr [rax+rax+00h]
0x1800548bd  test    eax, eax
0x1800548bf  jnz     short loc_1800548E3
0x1800548c1  call    cs:__imp_GetLastError
0x1800548c8  nop     dword ptr [rax+rax+00h]
0x1800548cd  lea     rdx, aInitializesdfr_3; "InitializeSdFromThreadToken: Get user i"...
0x1800548d4  mov     r8d, eax
0x1800548d7  mov     ebx, eax
0x1800548d9  mov     ecx, 8
0x1800548de  jmp     loc_18005476B
0x1800548e3  mov     r9d, [rbp+57h+var_7C]; TokenInformationLength
0x1800548e7  lea     rax, [rbp+57h+var_7C]
0x1800548eb  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800548ef  add     rbx, r14
0x1800548f2  mov     r8, rbx; TokenInformation
0x1800548f5  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1800548fa  mov     edx, 5; TokenInformationClass
0x1800548ff  call    cs:__imp_GetTokenInformation
0x180054906  nop     dword ptr [rax+rax+00h]
0x18005490b  test    eax, eax
0x18005490d  jnz     short loc_180054924
0x18005490f  call    cs:__imp_GetLastError
0x180054916  nop     dword ptr [rax+rax+00h]
0x18005491b  lea     rdx, aInitializesdfr_12; "InitializeSdFromThreadToken: Get group "...
0x180054922  jmp     short loc_1800548D4
0x180054924  mov     rdx, [r14]; pOwner
0x180054927  xor     r8d, r8d; bOwnerDefaulted
0x18005492a  mov     rcx, rdi; pSecurityDescriptor
0x18005492d  call    cs:__imp_SetSecurityDescriptorOwner
0x180054934  nop     dword ptr [rax+rax+00h]
0x180054939  test    eax, eax
0x18005493b  jnz     short loc_180054952
0x18005493d  call    cs:__imp_GetLastError
0x180054944  nop     dword ptr [rax+rax+00h]
0x180054949  lea     rdx, aInitializesdfr_2; "InitializeSdFromThreadToken: Set owner "...
0x180054950  jmp     short loc_1800548D4
0x180054952  mov     rdx, [rbx]; pGroup
0x180054955  xor     r8d, r8d; bGroupDefaulted
0x180054958  mov     rcx, rdi; pSecurityDescriptor
0x18005495b  call    cs:__imp_SetSecurityDescriptorGroup
0x180054962  nop     dword ptr [rax+rax+00h]
0x180054967  test    eax, eax
0x180054969  jnz     short loc_180054983
0x18005496b  call    cs:__imp_GetLastError
0x180054972  nop     dword ptr [rax+rax+00h]
0x180054977  lea     rdx, aInitializesdfr_6; "InitializeSdFromThreadToken: Set group "...
0x18005497e  jmp     loc_1800548D4
0x180054983  lea     rax, [rbp+57h+var_70]
0x180054987  mov     r14d, 1
0x18005498d  mov     [rsp+0E0h+Sid], rax; Sid
0x180054992  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180054996  mov     [rsp+0E0h+SubAuthority7], r13d; SubAuthority7
0x18005499b  mov     r9d, r14d; SubAuthority1
0x18005499e  mov     [rsp+0E0h+SubAuthority6], r13d; SubAuthority6
0x1800549a3  mov     [rsp+0E0h+SubAuthority5], r13d; SubAuthority5
0x1800549a8  lea     r8d, [r14+1]; SubAuthority0
0x1800549ac  mov     [rsp+0E0h+SubAuthority4], r13d; SubAuthority4
0x1800549b1  mov     dl, r8b; SubAuthorityCount
0x1800549b4  mov     [rsp+0E0h+SubAuthority3], r13d; SubAuthority3
0x1800549b9  mov     dword ptr [rsp+0E0h+ReturnLength], r13d; SubAuthority2
0x1800549be  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800549c5  nop     dword ptr [rax+rax+00h]
0x1800549ca  test    eax, eax
0x1800549cc  jns     short loc_1800549E8
0x1800549ce  mov     ecx, eax; Status
0x1800549d0  call    cs:__imp_RtlNtStatusToDosError
0x1800549d7  nop     dword ptr [rax+rax+00h]
0x1800549dc  lea     rdx, aInitializesdfr; "InitializeSdFromThreadToken: Failed to "...
0x1800549e3  jmp     loc_1800548D4
0x1800549e8  mov     rcx, [rbp+57h+var_70]; Sid
0x1800549ec  call    cs:__imp_RtlLengthSid
0x1800549f3  nop     dword ptr [rax+rax+00h]
0x1800549f8  lea     rcx, [rbp+57h+var_50]; Sid
0x1800549fc  mov     ebx, eax
0x1800549fe  call    cs:__imp_RtlLengthSid
0x180054a05  nop     dword ptr [rax+rax+00h]
0x180054a0a  lea     rcx, [rbp+57h+var_60]; Sid
0x180054a0e  add     ebx, eax
0x180054a10  call    cs:__imp_RtlLengthSid
0x180054a17  nop     dword ptr [rax+rax+00h]
0x180054a1c  add     eax, 20h ; ' '
0x180054a1f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180054a26  add     ebx, eax
0x180054a28  mov     ecx, ebx; unsigned __int64
0x180054a2a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180054a2f  mov     rsi, rax
0x180054a32  test    rax, rax
0x180054a35  jnz     short loc_180054A4B
0x180054a37  lea     ebx, [rax+8]
0x180054a3a  mov     r8d, ebx
0x180054a3d  lea     rdx, aInitializesdfr_4; "InitializeSdFromThreadToken: Memory all"...
0x180054a44  mov     ecx, ebx
0x180054a46  jmp     loc_18005476B
0x180054a4b  mov     r8d, 2; AclRevision
0x180054a51  mov     edx, ebx; AclSize
0x180054a53  mov     rcx, rsi; Acl
0x180054a56  call    cs:__imp_RtlCreateAcl
0x180054a5d  nop     dword ptr [rax+rax+00h]
0x180054a62  mov     ebx, 2
0x180054a67  lea     r9, [rbp+57h+var_60]; Sid
0x180054a6b  mov     edx, ebx; Revision
0x180054a6d  mov     r8d, r14d; AccessMask
0x180054a70  mov     rcx, rsi; Acl
0x180054a73  call    cs:__imp_RtlAddAccessAllowedAce
0x180054a7a  nop     dword ptr [rax+rax+00h]
0x180054a7f  lea     r9, [rbp+57h+var_50]; Sid
0x180054a83  mov     r8d, r14d; AccessMask
0x180054a86  mov     edx, ebx; Revision
0x180054a88  mov     rcx, rsi; Acl
0x180054a8b  call    cs:__imp_RtlAddAccessAllowedAce
0x180054a92  nop     dword ptr [rax+rax+00h]
0x180054a97  mov     r9, [rbp+57h+var_70]; Sid
0x180054a9b  mov     r8d, r14d; AccessMask
0x180054a9e  mov     edx, ebx; Revision
0x180054aa0  mov     rcx, rsi; Acl
0x180054aa3  call    cs:__imp_RtlAddAccessAllowedAce
0x180054aaa  nop     dword ptr [rax+rax+00h]
0x180054aaf  xor     r9d, r9d; bDaclDefaulted
0x180054ab2  mov     r8, rsi; pDacl
0x180054ab5  mov     edx, r14d; bDaclPresent
0x180054ab8  mov     rcx, rdi; pSecurityDescriptor
0x180054abb  call    cs:__imp_SetSecurityDescriptorDacl
0x180054ac2  nop     dword ptr [rax+rax+00h]
0x180054ac7  test    eax, eax
0x180054ac9  jnz     short loc_180054AE3
0x180054acb  call    cs:__imp_GetLastError
0x180054ad2  nop     dword ptr [rax+rax+00h]
0x180054ad7  lea     rdx, aInitializesdfr_8; "InitializeSdFromThreadToken: Set DACL o"...
0x180054ade  jmp     loc_1800548D4
0x180054ae3  mov     [r15], rdi
0x180054ae6  mov     ebx, r13d
0x180054ae9  mov     [r12], rsi
0x180054aed  mov     rdi, r13
0x180054af0  mov     rsi, r13
0x180054af3  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180054af7  test    rcx, rcx
0x180054afa  jz      short loc_180054B08
0x180054afc  call    cs:__imp_CloseHandle
0x180054b03  nop     dword ptr [rax+rax+00h]
0x180054b08  test    rdi, rdi
0x180054b0b  jz      short loc_180054B15
0x180054b0d  mov     rcx, rdi; void *
0x180054b10  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180054b15  test    rsi, rsi
0x180054b18  jz      short loc_180054B22
0x180054b1a  mov     rcx, rsi; void *
0x180054b1d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180054b22  mov     rcx, [rbp+57h+var_70]; Sid
0x180054b26  test    rcx, rcx
0x180054b29  jz      short loc_180054B37
0x180054b2b  call    cs:__imp_RtlFreeSid
0x180054b32  nop     dword ptr [rax+rax+00h]
0x180054b37  test    ebx, ebx
0x180054b39  jle     short loc_180054B44
0x180054b3b  movzx   ebx, bx
0x180054b3e  or      ebx, 80070000h
0x180054b44  mov     eax, ebx
0x180054b46  mov     rcx, [rbp+57h+var_40]
  ... truncated ...
```
