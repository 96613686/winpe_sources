# Int_NetworkIsolationVerifyPresenceOfCapabilities(void *,int *)

- ea: `0x18004d3d0`
- end: `0x18004d607`
- name: `?Int_NetworkIsolationVerifyPresenceOfCapabilities@@YAKPEAXPEAH@Z`
- size: `567`
- prototype: `unsigned int __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180057760`
- `0x1800578e0`

## callees

- `0x180005e0c`
- `0x1800294b0`
- `0x18004d3d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d47d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d4fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d47d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d4fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d598`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18004d588`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18004d588`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18004d4ec`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18004d4ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004d423`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004d423`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004d46d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004d46d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004d455`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004d455`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004d441`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004d441`
- `fwbase!FwCloseHandle` at `0x18004d539`
- `fwbase!FwCloseHandle` at `0x18004d5d9`
- `fwbase!FwCloseHandle` at `0x18004d539`
- `fwbase!FwCloseHandle` at `0x18004d5d9`

## pseudocode

```c
__int64 __fastcall Int_NetworkIsolationVerifyPresenceOfCapabilities(PSECURITY_DESCRIPTOR pSecurityDescriptor, int *a2)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  FwPolicy2 *v7; // rcx
  __int64 v8; // rdx
  void *v9; // rdx
  void *TokenHandle; // [rsp+40h] [rbp-9h] BYREF
  void *phNewToken; // [rsp+48h] [rbp-1h] BYREF
  WINBOOL AccessStatus; // [rsp+50h] [rbp+7h] BYREF
  DWORD GrantedAccess; // [rsp+54h] [rbp+Bh] BYREF
  DWORD PrivilegeSetLength; // [rsp+58h] [rbp+Fh] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+60h] [rbp+17h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+70h] [rbp+27h] BYREF

  PrivilegeSetLength = 20;
  TokenHandle = 0;
  phNewToken = 0;
  *(_QWORD *)&GenericMapping.GenericRead = 0;
  *(_QWORD *)&GenericMapping.GenericExecute = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  GrantedAccess = 0;
  AccessStatus = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    v9 = TokenHandle;
LABEL_13:
    if ( AccessCheck(
           pSecurityDescriptor,
           v9,
           0x20000u,
           &GenericMapping,
           &PrivilegeSet,
           &PrivilegeSetLength,
           &GrantedAccess,
           &AccessStatus) )
    {
      LastError = 0;
      *a2 = AccessStatus;
    }
    else
    {
      LastError = GetLastError();
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 522;
        goto LABEL_6;
      }
    }
    goto LABEL_18;
  }
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0xEu, &TokenHandle) )
  {
    LastError = GetLastError();
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 519;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, LastError);
      goto LABEL_18;
    }
    goto LABEL_18;
  }
  if ( DuplicateTokenEx(TokenHandle, 0xCu, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
  {
    FwCloseHandle(TokenHandle);
    v9 = phNewToken;
    TokenHandle = phNewToken;
    phNewToken = 0;
    goto LABEL_13;
  }
  LastError = GetLastError();
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v8 = 520;
    goto LABEL_6;
  }
LABEL_18:
  if ( TokenHandle )
    FwCloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18004d3d0  mov     [rsp-8+arg_10], rbx
0x18004d3d5  push    rbp
0x18004d3d6  push    rsi
0x18004d3d7  push    rdi
0x18004d3d8  lea     rbp, [rsp-47h]
0x18004d3dd  sub     rsp, 90h
0x18004d3e4  mov     rax, cs:__security_cookie
0x18004d3eb  xor     rax, rsp
0x18004d3ee  mov     [rbp+57h+var_18], rax
0x18004d3f2  xor     esi, esi
0x18004d3f4  mov     [rbp+57h+PrivilegeSetLength], 14h
0x18004d3fb  xorps   xmm0, xmm0
0x18004d3fe  mov     [rbp+57h+TokenHandle], rsi
0x18004d402  xor     eax, eax
0x18004d404  mov     [rbp+57h+var_58], rsi
0x18004d408  mov     qword ptr [rbp+57h+GenericMapping.GenericRead], rsi
0x18004d40c  mov     rdi, rdx
0x18004d40f  mov     qword ptr [rbp+57h+GenericMapping.GenericExecute], rsi
0x18004d413  mov     rbx, rcx
0x18004d416  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x18004d41a  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x18004d41d  mov     [rbp+57h+var_4C], esi
0x18004d420  mov     [rbp+57h+var_50], esi
0x18004d423  call    cs:__imp_GetCurrentThread
0x18004d42a  nop     dword ptr [rax+rax+00h]
0x18004d42f  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18004d433  mov     edx, 0Ch; DesiredAccess
0x18004d438  mov     rcx, rax; ThreadHandle
0x18004d43b  mov     r8d, 1; OpenAsSelf
0x18004d441  call    cs:__imp_OpenThreadToken
0x18004d448  nop     dword ptr [rax+rax+00h]
0x18004d44d  test    eax, eax
0x18004d44f  jnz     loc_18004D553
0x18004d455  call    cs:__imp_GetCurrentProcess
0x18004d45c  nop     dword ptr [rax+rax+00h]
0x18004d461  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18004d465  mov     edx, 0Eh; DesiredAccess
0x18004d46a  mov     rcx, rax; ProcessHandle
0x18004d46d  call    cs:__imp_OpenProcessToken
0x18004d474  nop     dword ptr [rax+rax+00h]
0x18004d479  test    eax, eax
0x18004d47b  jnz     short loc_18004D4C9
0x18004d47d  call    cs:__imp_GetLastError
0x18004d484  nop     dword ptr [rax+rax+00h]
0x18004d489  mov     ebx, eax
0x18004d48b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d492  lea     rax, WPP_GLOBAL_Control
0x18004d499  cmp     rcx, rax
0x18004d49c  jz      loc_18004D5D0
0x18004d4a2  test    byte ptr [rcx+1Ch], 1
0x18004d4a6  jz      loc_18004D5D0
0x18004d4ac  mov     edx, 207h
0x18004d4b1  mov     rcx, [rcx+10h]
0x18004d4b5  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18004d4bc  mov     r9d, ebx
0x18004d4bf  call    WPP_SF_d
0x18004d4c4  jmp     loc_18004D5D0
0x18004d4c9  mov     rcx, [rbp+57h+TokenHandle]; hExistingToken
0x18004d4cd  lea     rax, [rbp+57h+var_58]
0x18004d4d1  mov     [rsp+0A0h+phNewToken], rax; phNewToken
0x18004d4d6  mov     r9d, 2; ImpersonationLevel
0x18004d4dc  xor     r8d, r8d; lpTokenAttributes
0x18004d4df  mov     [rsp+0A0h+TokenType], 2; TokenType
0x18004d4e7  mov     edx, 0Ch; dwDesiredAccess
0x18004d4ec  call    cs:__imp_DuplicateTokenEx
0x18004d4f3  nop     dword ptr [rax+rax+00h]
0x18004d4f8  test    eax, eax
0x18004d4fa  jnz     short loc_18004D535
0x18004d4fc  call    cs:__imp_GetLastError
0x18004d503  nop     dword ptr [rax+rax+00h]
0x18004d508  mov     ebx, eax
0x18004d50a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d511  lea     rax, WPP_GLOBAL_Control
0x18004d518  cmp     rcx, rax
0x18004d51b  jz      loc_18004D5D0
0x18004d521  test    byte ptr [rcx+1Ch], 1
0x18004d525  jz      loc_18004D5D0
0x18004d52b  mov     edx, 208h
0x18004d530  jmp     loc_18004D4B1
0x18004d535  mov     rcx, [rbp+57h+TokenHandle]
0x18004d539  call    cs:__imp_FwCloseHandle
0x18004d540  nop     dword ptr [rax+rax+00h]
0x18004d545  mov     rdx, [rbp+57h+var_58]
0x18004d549  mov     [rbp+57h+TokenHandle], rdx
0x18004d54d  mov     [rbp+57h+var_58], rsi
0x18004d551  jmp     short loc_18004D557
0x18004d553  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x18004d557  lea     rax, [rbp+57h+var_50]
0x18004d55b  mov     r8d, 20000h; DesiredAccess
0x18004d561  mov     [rsp+0A0h+AccessStatus], rax; AccessStatus
0x18004d566  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18004d56a  lea     rax, [rbp+57h+var_4C]
0x18004d56e  mov     rcx, rbx; pSecurityDescriptor
0x18004d571  mov     [rsp+0A0h+GrantedAccess], rax; GrantedAccess
0x18004d576  lea     rax, [rbp+57h+PrivilegeSetLength]
0x18004d57a  mov     [rsp+0A0h+phNewToken], rax; PrivilegeSetLength
0x18004d57f  lea     rax, [rbp+57h+PrivilegeSet]
0x18004d583  mov     qword ptr [rsp+0A0h+TokenType], rax; PrivilegeSet
0x18004d588  call    cs:__imp_AccessCheck
0x18004d58f  nop     dword ptr [rax+rax+00h]
0x18004d594  test    eax, eax
0x18004d596  jnz     short loc_18004D5C9
0x18004d598  call    cs:__imp_GetLastError
0x18004d59f  nop     dword ptr [rax+rax+00h]
0x18004d5a4  mov     ebx, eax
0x18004d5a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d5ad  lea     rax, WPP_GLOBAL_Control
0x18004d5b4  cmp     rcx, rax
0x18004d5b7  jz      short loc_18004D5D0
0x18004d5b9  test    byte ptr [rcx+1Ch], 1
0x18004d5bd  jz      short loc_18004D5D0
0x18004d5bf  mov     edx, 20Ah
0x18004d5c4  jmp     loc_18004D4B1
0x18004d5c9  mov     eax, [rbp+57h+var_50]
0x18004d5cc  mov     ebx, esi
0x18004d5ce  mov     [rdi], eax
0x18004d5d0  mov     rcx, [rbp+57h+TokenHandle]
0x18004d5d4  test    rcx, rcx
0x18004d5d7  jz      short loc_18004D5E5
0x18004d5d9  call    cs:__imp_FwCloseHandle
0x18004d5e0  nop     dword ptr [rax+rax+00h]
0x18004d5e5  mov     eax, ebx
0x18004d5e7  mov     rcx, [rbp+57h+var_18]
0x18004d5eb  xor     rcx, rsp; StackCookie
0x18004d5ee  call    __security_check_cookie
0x18004d5f3  mov     rbx, [rsp+0A0h+arg_10]
0x18004d5fb  add     rsp, 90h
0x18004d602  pop     rdi
0x18004d603  pop     rsi
0x18004d604  pop     rbp
0x18004d605  retn
```
