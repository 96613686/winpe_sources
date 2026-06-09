# IsUserInAdminGroup(void)

- ea: `0x1800823cc`
- end: `0x180082550`
- name: `?IsUserInAdminGroup@@YAHXZ`
- size: `388`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180072fa0`

## callees

- `0x1800823cc`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008242b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008242b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008243b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008243b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008240d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008240d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180082421`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180082421`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082514`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008252b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082514`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008252b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008246a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180082499`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008246a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180082499`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800824d4`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800824d4`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800824b6`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800824b6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800824ed`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800824ed`

## pseudocode

```c
__int64 IsUserInAdminGroup(void)
{
  __int64 result; // rax
  unsigned int v1; // ebx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-39h] BYREF
  int TokenInformation; // [rsp+38h] [rbp-31h] BYREF
  DWORD ReturnLength; // [rsp+3Ch] [rbp-2Dh] BYREF
  WINBOOL IsMember; // [rsp+40h] [rbp-29h] BYREF
  void *DuplicateTokenHandle; // [rsp+48h] [rbp-21h] BYREF
  DWORD cbSid[4]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE pSid[80]; // [rsp+60h] [rbp-9h] BYREF

  result = (unsigned int)dword_1802975F4;
  DuplicateTokenHandle = 0;
  TokenHandle = 0;
  if ( dword_1802975F4 == 2 )
  {
    v1 = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xAu, 1, &TokenHandle)
      || (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle)) )
    {
      TokenInformation = 0;
      ReturnLength = 0;
      if ( GetTokenInformation(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength) )
      {
        if ( (TokenInformation != 3
           || GetTokenInformation(TokenHandle, TokenLinkedToken, &DuplicateTokenHandle, 8u, &ReturnLength))
          && (DuplicateTokenHandle || DuplicateToken(TokenHandle, SecurityIdentification, &DuplicateTokenHandle)) )
        {
          cbSid[0] = 68;
          if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, cbSid) )
          {
            IsMember = 0;
            if ( CheckTokenMembership(DuplicateTokenHandle, pSid, &IsMember) )
            {
              if ( IsMember )
              {
                dword_1802975F4 = 1;
                v1 = 1;
              }
            }
          }
        }
      }
    }
    if ( TokenHandle )
    {
      CloseHandle(TokenHandle);
      TokenHandle = 0;
    }
    if ( DuplicateTokenHandle )
      CloseHandle(DuplicateTokenHandle);
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x1800823cc  mov     [rsp-8+arg_0], rbx
0x1800823d1  push    rbp
0x1800823d2  lea     rbp, [rsp-57h]
0x1800823d7  sub     rsp, 0C0h
0x1800823de  mov     rax, cs:__security_cookie
0x1800823e5  xor     rax, rsp
0x1800823e8  mov     [rbp+57h+var_10], rax
0x1800823ec  mov     eax, cs:dword_1802975F4
0x1800823f2  mov     [rbp+57h+DuplicateTokenHandle], 0
0x1800823fa  mov     [rbp+57h+TokenHandle], 0
0x180082402  cmp     eax, 2
0x180082405  jnz     loc_180082533
0x18008240b  xor     ebx, ebx
0x18008240d  call    cs:__imp_GetCurrentThread
0x180082413  mov     rcx, rax; ThreadHandle
0x180082416  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18008241a  lea     edx, [rbx+0Ah]; DesiredAccess
0x18008241d  lea     r8d, [rbx+1]; OpenAsSelf
0x180082421  call    cs:__imp_OpenThreadToken
0x180082427  test    eax, eax
0x180082429  jnz     short loc_180082449
0x18008242b  call    cs:__imp_GetCurrentProcess
0x180082431  mov     rcx, rax; ProcessHandle
0x180082434  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180082438  lea     edx, [rbx+0Ah]; DesiredAccess
0x18008243b  call    cs:__imp_OpenProcessToken
0x180082441  test    eax, eax
0x180082443  jz      loc_18008250B
0x180082449  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18008244d  lea     rax, [rbp+57h+var_84]
0x180082451  mov     r9d, 4; TokenInformationLength
0x180082457  mov     [rbp+57h+TokenInformation], ebx
0x18008245a  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18008245e  mov     [rbp+57h+var_84], ebx
0x180082461  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180082466  lea     edx, [r9+0Eh]; TokenInformationClass
0x18008246a  call    cs:__imp_GetTokenInformation
0x180082470  test    eax, eax
0x180082472  jz      loc_18008250B
0x180082478  cmp     [rbp+57h+TokenInformation], 3
0x18008247c  jnz     short loc_1800824A3
0x18008247e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180082482  lea     rax, [rbp+57h+var_84]
0x180082486  mov     r9d, 8; TokenInformationLength
0x18008248c  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180082491  lea     r8, [rbp+57h+DuplicateTokenHandle]; TokenInformation
0x180082495  lea     edx, [r9+0Bh]; TokenInformationClass
0x180082499  call    cs:__imp_GetTokenInformation
0x18008249f  test    eax, eax
0x1800824a1  jz      short loc_18008250B
0x1800824a3  cmp     [rbp+57h+DuplicateTokenHandle], rbx
0x1800824a7  jnz     short loc_1800824C0
0x1800824a9  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x1800824ad  lea     r8, [rbp+57h+DuplicateTokenHandle]; DuplicateTokenHandle
0x1800824b1  mov     edx, 1; ImpersonationLevel
0x1800824b6  call    cs:__imp_DuplicateToken
0x1800824bc  test    eax, eax
0x1800824be  jz      short loc_18008250B
0x1800824c0  xor     edx, edx; DomainSid
0x1800824c2  mov     [rbp+57h+cbSid], 44h ; 'D'
0x1800824c9  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800824cd  lea     r8, [rbp+57h+pSid]; pSid
0x1800824d1  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800824d4  call    cs:__imp_CreateWellKnownSid
0x1800824da  test    eax, eax
0x1800824dc  jz      short loc_18008250B
0x1800824de  mov     rcx, [rbp+57h+DuplicateTokenHandle]; TokenHandle
0x1800824e2  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800824e6  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x1800824ea  mov     [rbp+57h+IsMember], ebx
0x1800824ed  call    cs:__imp_CheckTokenMembership
0x1800824f3  test    eax, eax
0x1800824f5  jz      short loc_18008250B
0x1800824f7  cmp     [rbp+57h+IsMember], ebx
0x1800824fa  jz      short loc_18008250B
0x1800824fc  mov     cs:dword_1802975F4, 1
0x180082506  mov     ebx, 1
0x18008250b  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18008250f  test    rcx, rcx
0x180082512  jz      short loc_180082522
0x180082514  call    cs:__imp_CloseHandle
0x18008251a  mov     [rbp+57h+TokenHandle], 0
0x180082522  mov     rcx, [rbp+57h+DuplicateTokenHandle]; hObject
0x180082526  test    rcx, rcx
0x180082529  jz      short loc_180082531
0x18008252b  call    cs:__imp_CloseHandle
0x180082531  mov     eax, ebx
0x180082533  mov     rcx, [rbp+57h+var_10]
0x180082537  xor     rcx, rsp; StackCookie
0x18008253a  call    __security_check_cookie
0x18008253f  mov     rbx, [rsp+0C0h+arg_0]
0x180082547  add     rsp, 0C0h
0x18008254e  pop     rbp
0x18008254f  retn
```
