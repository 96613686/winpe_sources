# CPolicyMonitor::InitializeSdFromThreadToken(void * *,_ACL * *)

- ea: `0x180050fd4`
- end: `0x180051413`
- name: `?InitializeSdFromThreadToken@CPolicyMonitor@@CAJPEAPEAXPEAPEAU_ACL@@@Z`
- size: `1087`
- prototype: `__int64 __fastcall(void **, struct _ACL **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180047e7c`

## callees

- `0x1800074c0`
- `0x18004b460`
- `0x18004b830`
- `0x18004b890`
- `0x180050fd4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800512be`
- `ntdll!RtlNtStatusToDosError` at `0x1800512be`
- `ntdll!RtlFreeSid` at `0x1800513d7`
- `ntdll!RtlFreeSid` at `0x1800513d7`
- `ntdll!RtlAddAccessAllowedAce` at `0x180051343`
- `ntdll!RtlAddAccessAllowedAce` at `0x180051355`
- `ntdll!RtlAddAccessAllowedAce` at `0x180051367`
- `ntdll!RtlAddAccessAllowedAce` at `0x180051343`
- `ntdll!RtlAddAccessAllowedAce` at `0x180051355`
- `ntdll!RtlAddAccessAllowedAce` at `0x180051367`
- `ntdll!RtlCreateAcl` at `0x18005132c`
- `ntdll!RtlCreateAcl` at `0x18005132c`
- `ntdll!RtlLengthSid` at `0x1800512d4`
- `ntdll!RtlLengthSid` at `0x1800512e0`
- `ntdll!RtlLengthSid` at `0x1800512ec`
- `ntdll!RtlLengthSid` at `0x1800512d4`
- `ntdll!RtlLengthSid` at `0x1800512e0`
- `ntdll!RtlLengthSid` at `0x1800512ec`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800512b2`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800512b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005109e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800510e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005111e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800511a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800511df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051243`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051265`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051383`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005109e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800510e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005111e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800511a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800511df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051243`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051265`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051383`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005106b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005106b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180051054`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180051054`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180051094`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180051094`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180051084`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180051084`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800513ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800513ae`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005119c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005119c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180051379`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180051379`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800510dd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180051114`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800511d5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180051217`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800510dd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180051114`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800511d5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180051217`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180051239`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180051239`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18005125b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18005125b`

## string_xrefs

- `0x1800510a4`: `InitializeSdFromThreadToken: Unable to open thread/process token, status %d`
- `0x1800510bd`: `InitializeSdFromThreadToken: Unable to open thread token, status %d`
- `0x1800510f4`: `InitializeSdFromThreadToken: Get user info from token for size failed, status %d`
- `0x18005112b`: `InitializeSdFromThreadToken: Get group info from token for size failed, status %d`
- `0x180051156`: `InitializeSdFromThreadToken: Buffer size too small: %d < %d`
- `0x180051185`: `InitializeSdFromThreadToken: Memory allocation for output buffer failed, status %d`
- `0x1800511ac`: `InitializeSdFromThreadToken: Initialize SD failed, status %d`
- `0x1800511e5`: `InitializeSdFromThreadToken: Get user info from token failed, status %d`
- `0x180051227`: `InitializeSdFromThreadToken: Get group info from token failed, status %d`
- `0x180051249`: `InitializeSdFromThreadToken: Set owner on SD failed, status %d`
- `0x18005126b`: `InitializeSdFromThreadToken: Set group on SD failed, status %d`
- `0x1800512c4`: `InitializeSdFromThreadToken: Failed to allocate packge SID: %d`
- `0x180051313`: `InitializeSdFromThreadToken: Memory allocation for the ACL failed, status %d`
- `0x180051389`: `InitializeSdFromThreadToken: Set DACL on SD failed, status %d`

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
0x180050fd4  mov     [rsp-8+arg_10], rbx
0x180050fd9  push    rbp
0x180050fda  push    rsi
0x180050fdb  push    rdi
0x180050fdc  push    r12
0x180050fde  push    r13
0x180050fe0  push    r14
0x180050fe2  push    r15
0x180050fe4  lea     rbp, [rsp-27h]
0x180050fe9  sub     rsp, 0B0h
0x180050ff0  mov     rax, cs:__security_cookie
0x180050ff7  xor     rax, rsp
0x180050ffa  mov     [rbp+57h+var_40], rax
0x180050ffe  xor     r13d, r13d
0x180051001  mov     [rbp+57h+var_60], 101h
0x180051008  mov     [rbp+57h+TokenHandle], r13
0x18005100c  mov     edi, r13d
0x18005100f  mov     [rbp+57h+TokenInformationLength], r13d
0x180051013  mov     esi, r13d
0x180051016  mov     [rbp+57h+var_7C], r13d
0x18005101a  mov     r12, rdx
0x18005101d  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r13d
0x180051021  mov     r15, rcx
0x180051024  mov     [rbp+57h+var_70], r13
0x180051028  mov     [rcx], r13
0x18005102b  mov     [rbp+57h+var_5C], 5000000h
0x180051032  mov     [rbp+57h+var_58], 0Bh
0x180051039  mov     [rbp+57h+var_50], 101h
0x180051040  mov     [rbp+57h+var_4C], 5000000h
0x180051047  mov     [rbp+57h+var_48], 4
0x18005104e  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 0F00h
0x180051054  call    cs:__imp_GetCurrentThread
0x18005105a  lea     r14d, [r13+8]
0x18005105e  xor     r8d, r8d; OpenAsSelf
0x180051061  mov     rcx, rax; ThreadHandle
0x180051064  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180051068  mov     edx, r14d; DesiredAccess
0x18005106b  call    cs:__imp_OpenThreadToken
0x180051071  test    eax, eax
0x180051073  jnz     short loc_1800510C6
0x180051075  call    cs:__imp_GetLastError
0x18005107b  mov     ebx, eax
0x18005107d  cmp     eax, 3F0h
0x180051082  jnz     short loc_1800510BD
0x180051084  call    cs:__imp_GetCurrentProcess
0x18005108a  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18005108e  mov     edx, r14d; DesiredAccess
0x180051091  mov     rcx, rax; ProcessHandle
0x180051094  call    cs:__imp_OpenProcessToken
0x18005109a  test    eax, eax
0x18005109c  jnz     short loc_1800510C6
0x18005109e  call    cs:__imp_GetLastError
0x1800510a4  lea     rdx, aInitializesdfr_10; "InitializeSdFromThreadToken: Unable to "...
0x1800510ab  mov     ebx, eax
0x1800510ad  mov     r8d, eax
0x1800510b0  mov     ecx, r14d; int
0x1800510b3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800510b8  jmp     loc_1800513A5
0x1800510bd  lea     rdx, aInitializesdfr_9; "InitializeSdFromThreadToken: Unable to "...
0x1800510c4  jmp     short loc_1800510AD
0x1800510c6  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800510ca  lea     rax, [rbp+57h+TokenInformationLength]
0x1800510ce  xor     r9d, r9d; TokenInformationLength
0x1800510d1  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1800510d6  xor     r8d, r8d; TokenInformation
0x1800510d9  lea     edx, [r9+1]; TokenInformationClass
0x1800510dd  call    cs:__imp_GetTokenInformation
0x1800510e3  test    eax, eax
0x1800510e5  jnz     short loc_1800510FD
0x1800510e7  call    cs:__imp_GetLastError
0x1800510ed  mov     ebx, eax
0x1800510ef  cmp     eax, 7Ah ; 'z'
0x1800510f2  jz      short loc_1800510FD
0x1800510f4  lea     rdx, aInitializesdfr_5; "InitializeSdFromThreadToken: Get user i"...
0x1800510fb  jmp     short loc_1800510AD
0x1800510fd  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180051101  lea     rax, [rbp+57h+var_7C]
0x180051105  xor     r9d, r9d; TokenInformationLength
0x180051108  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18005110d  xor     r8d, r8d; TokenInformation
0x180051110  lea     edx, [r9+5]; TokenInformationClass
0x180051114  call    cs:__imp_GetTokenInformation
0x18005111a  test    eax, eax
0x18005111c  jnz     short loc_180051137
0x18005111e  call    cs:__imp_GetLastError
0x180051124  mov     ebx, eax
0x180051126  cmp     eax, 7Ah ; 'z'
0x180051129  jz      short loc_180051137
0x18005112b  lea     rdx, aInitializesdfr_7; "InitializeSdFromThreadToken: Get group "...
0x180051132  jmp     loc_1800510AD
0x180051137  mov     ebx, [rbp+57h+TokenInformationLength]
0x18005113a  mov     r9d, 40h ; '@'
0x180051140  mov     ecx, [rbp+57h+var_7C]
0x180051143  add     ebx, 7
0x180051146  and     ebx, 0FFFFFFF8h
0x180051149  add     ecx, 28h ; '('
0x18005114c  add     ecx, ebx; unsigned __int64
0x18005114e  cmp     ecx, r9d
0x180051151  jnb     short loc_18005116E
0x180051153  mov     r8d, ecx
0x180051156  lea     rdx, aInitializesdfr_0; "InitializeSdFromThreadToken: Buffer siz"...
0x18005115d  mov     ecx, r14d; int
0x180051160  lea     ebx, [r9+3Ah]
0x180051164  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180051169  jmp     loc_1800513A5
0x18005116e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180051175  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005117a  mov     rdi, rax
0x18005117d  test    rax, rax
0x180051180  jnz     short loc_180051194
0x180051182  mov     ebx, r14d
0x180051185  lea     rdx, aInitializesdfr_11; "InitializeSdFromThreadToken: Memory all"...
0x18005118c  mov     r8d, r14d
0x18005118f  jmp     loc_1800510B0
0x180051194  mov     edx, 1; dwRevision
0x180051199  mov     rcx, rdi; pSecurityDescriptor
0x18005119c  call    cs:__imp_InitializeSecurityDescriptor
0x1800511a2  test    eax, eax
0x1800511a4  jnz     short loc_1800511B8
0x1800511a6  call    cs:__imp_GetLastError
0x1800511ac  lea     rdx, aInitializesdfr_1; "InitializeSdFromThreadToken: Initialize"...
0x1800511b3  jmp     loc_1800510AB
0x1800511b8  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1800511bc  lea     rax, [rbp+57h+TokenInformationLength]
0x1800511c0  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800511c4  lea     r14, [rdi+28h]
0x1800511c8  mov     r8, r14; TokenInformation
0x1800511cb  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1800511d0  mov     edx, 1; TokenInformationClass
0x1800511d5  call    cs:__imp_GetTokenInformation
0x1800511db  test    eax, eax
0x1800511dd  jnz     short loc_1800511FB
0x1800511df  call    cs:__imp_GetLastError
0x1800511e5  lea     rdx, aInitializesdfr_3; "InitializeSdFromThreadToken: Get user i"...
0x1800511ec  mov     r8d, eax
0x1800511ef  mov     ebx, eax
0x1800511f1  mov     ecx, 8
0x1800511f6  jmp     loc_1800510B3
0x1800511fb  mov     r9d, [rbp+57h+var_7C]; TokenInformationLength
0x1800511ff  lea     rax, [rbp+57h+var_7C]
0x180051203  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180051207  add     rbx, r14
0x18005120a  mov     r8, rbx; TokenInformation
0x18005120d  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180051212  mov     edx, 5; TokenInformationClass
0x180051217  call    cs:__imp_GetTokenInformation
0x18005121d  test    eax, eax
0x18005121f  jnz     short loc_180051230
0x180051221  call    cs:__imp_GetLastError
0x180051227  lea     rdx, aInitializesdfr_12; "InitializeSdFromThreadToken: Get group "...
0x18005122e  jmp     short loc_1800511EC
0x180051230  mov     rdx, [r14]; pOwner
0x180051233  xor     r8d, r8d; bOwnerDefaulted
0x180051236  mov     rcx, rdi; pSecurityDescriptor
0x180051239  call    cs:__imp_SetSecurityDescriptorOwner
0x18005123f  test    eax, eax
0x180051241  jnz     short loc_180051252
0x180051243  call    cs:__imp_GetLastError
0x180051249  lea     rdx, aInitializesdfr_2; "InitializeSdFromThreadToken: Set owner "...
0x180051250  jmp     short loc_1800511EC
0x180051252  mov     rdx, [rbx]; pGroup
0x180051255  xor     r8d, r8d; bGroupDefaulted
0x180051258  mov     rcx, rdi; pSecurityDescriptor
0x18005125b  call    cs:__imp_SetSecurityDescriptorGroup
0x180051261  test    eax, eax
0x180051263  jnz     short loc_180051277
0x180051265  call    cs:__imp_GetLastError
0x18005126b  lea     rdx, aInitializesdfr_6; "InitializeSdFromThreadToken: Set group "...
0x180051272  jmp     loc_1800511EC
0x180051277  lea     rax, [rbp+57h+var_70]
0x18005127b  mov     r14d, 1
0x180051281  mov     [rsp+0E0h+Sid], rax; Sid
0x180051286  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18005128a  mov     [rsp+0E0h+SubAuthority7], r13d; SubAuthority7
0x18005128f  mov     r9d, r14d; SubAuthority1
0x180051292  mov     [rsp+0E0h+SubAuthority6], r13d; SubAuthority6
0x180051297  mov     [rsp+0E0h+SubAuthority5], r13d; SubAuthority5
0x18005129c  lea     r8d, [r14+1]; SubAuthority0
0x1800512a0  mov     [rsp+0E0h+SubAuthority4], r13d; SubAuthority4
0x1800512a5  mov     dl, r8b; SubAuthorityCount
0x1800512a8  mov     [rsp+0E0h+SubAuthority3], r13d; SubAuthority3
0x1800512ad  mov     dword ptr [rsp+0E0h+ReturnLength], r13d; SubAuthority2
0x1800512b2  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800512b8  test    eax, eax
0x1800512ba  jns     short loc_1800512D0
0x1800512bc  mov     ecx, eax; Status
0x1800512be  call    cs:__imp_RtlNtStatusToDosError
0x1800512c4  lea     rdx, aInitializesdfr; "InitializeSdFromThreadToken: Failed to "...
0x1800512cb  jmp     loc_1800511EC
0x1800512d0  mov     rcx, [rbp+57h+var_70]; Sid
0x1800512d4  call    cs:__imp_RtlLengthSid
0x1800512da  lea     rcx, [rbp+57h+var_50]; Sid
0x1800512de  mov     ebx, eax
0x1800512e0  call    cs:__imp_RtlLengthSid
0x1800512e6  lea     rcx, [rbp+57h+var_60]; Sid
0x1800512ea  add     ebx, eax
0x1800512ec  call    cs:__imp_RtlLengthSid
0x1800512f2  add     eax, 20h ; ' '
0x1800512f5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800512fc  add     ebx, eax
0x1800512fe  mov     ecx, ebx; unsigned __int64
0x180051300  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180051305  mov     rsi, rax
0x180051308  test    rax, rax
0x18005130b  jnz     short loc_180051321
0x18005130d  lea     ebx, [rax+8]
0x180051310  mov     r8d, ebx
0x180051313  lea     rdx, aInitializesdfr_4; "InitializeSdFromThreadToken: Memory all"...
0x18005131a  mov     ecx, ebx
0x18005131c  jmp     loc_1800510B3
0x180051321  mov     r8d, 2; AclRevision
0x180051327  mov     edx, ebx; AclSize
0x180051329  mov     rcx, rsi; Acl
0x18005132c  call    cs:__imp_RtlCreateAcl
0x180051332  mov     ebx, 2
0x180051337  lea     r9, [rbp+57h+var_60]; Sid
0x18005133b  mov     edx, ebx; Revision
0x18005133d  mov     r8d, r14d; AccessMask
0x180051340  mov     rcx, rsi; Acl
0x180051343  call    cs:__imp_RtlAddAccessAllowedAce
0x180051349  lea     r9, [rbp+57h+var_50]; Sid
0x18005134d  mov     r8d, r14d; AccessMask
0x180051350  mov     edx, ebx; Revision
0x180051352  mov     rcx, rsi; Acl
0x180051355  call    cs:__imp_RtlAddAccessAllowedAce
0x18005135b  mov     r9, [rbp+57h+var_70]; Sid
0x18005135f  mov     r8d, r14d; AccessMask
0x180051362  mov     edx, ebx; Revision
0x180051364  mov     rcx, rsi; Acl
0x180051367  call    cs:__imp_RtlAddAccessAllowedAce
0x18005136d  xor     r9d, r9d; bDaclDefaulted
0x180051370  mov     r8, rsi; pDacl
0x180051373  mov     edx, r14d; bDaclPresent
0x180051376  mov     rcx, rdi; pSecurityDescriptor
0x180051379  call    cs:__imp_SetSecurityDescriptorDacl
0x18005137f  test    eax, eax
0x180051381  jnz     short loc_180051395
0x180051383  call    cs:__imp_GetLastError
0x180051389  lea     rdx, aInitializesdfr_8; "InitializeSdFromThreadToken: Set DACL o"...
0x180051390  jmp     loc_1800511EC
0x180051395  mov     [r15], rdi
0x180051398  mov     ebx, r13d
0x18005139b  mov     [r12], rsi
0x18005139f  mov     rdi, r13
0x1800513a2  mov     rsi, r13
0x1800513a5  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800513a9  test    rcx, rcx
0x1800513ac  jz      short loc_1800513B4
0x1800513ae  call    cs:__imp_CloseHandle
0x1800513b4  test    rdi, rdi
0x1800513b7  jz      short loc_1800513C1
0x1800513b9  mov     rcx, rdi; void *
0x1800513bc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800513c1  test    rsi, rsi
0x1800513c4  jz      short loc_1800513CE
0x1800513c6  mov     rcx, rsi; void *
0x1800513c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800513ce  mov     rcx, [rbp+57h+var_70]; Sid
0x1800513d2  test    rcx, rcx
0x1800513d5  jz      short loc_1800513DD
0x1800513d7  call    cs:__imp_RtlFreeSid
0x1800513dd  test    ebx, ebx
0x1800513df  jle     short loc_1800513EA
0x1800513e1  movzx   ebx, bx
0x1800513e4  or      ebx, 80070000h
0x1800513ea  mov     eax, ebx
0x1800513ec  mov     rcx, [rbp+57h+var_40]
0x1800513f0  xor     rcx, rsp; StackCookie
0x1800513f3  call    __security_check_cookie
0x1800513f8  mov     rbx, [rsp+0E0h+arg_10]
0x180051400  add     rsp, 0B0h
0x180051407  pop     r15
0x180051409  pop     r14
0x18005140b  pop     r13
0x18005140d  pop     r12
0x18005140f  pop     rdi
0x180051410  pop     rsi
0x180051411  pop     rbp
0x180051412  retn
```
