# FolderAccessCheckOnThreadToken(ushort const *,ulong)

- ea: `0x180002ab0`
- end: `0x180002e90`
- name: `?FolderAccessCheckOnThreadToken@@YAJPEBGK@Z`
- size: `992`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, DWORD DesiredAccess)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180002530`
- `0x180009490`
- `0x18000f610`
- `0x18000f770`
- `0x18000f9e0`

## callees

- `0x180002ab0`
- `0x180009ef8`
- `0x180009f38`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180002b93`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180002be3`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180002ce3`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180002d3a`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180002b93`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180002be3`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180002ce3`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180002d3a`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180002b2b`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180002b2b`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180002c59`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180002db0`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180002c59`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180002db0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002c6f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002c6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002dcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002de9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002dcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002de9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002b02`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002b51`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002b02`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002b51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002aea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002b39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002aea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002b39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002c7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002c7f`

## pseudocode

```c
signed int __fastcall FolderAccessCheckOnThreadToken(LPCWSTR lpFileName, DWORD DesiredAccess)
{
  HANDLE CurrentThread; // rax
  signed int result; // eax
  unsigned int v6; // ebx
  HANDLE v7; // rax
  void *v8; // r12
  signed int v9; // eax
  void *v10; // rsi
  void *v11; // r12
  signed int v12; // eax
  void *v13; // rsi
  signed int v14; // eax
  signed int LastError; // eax
  DWORD nLengthNeeded; // [rsp+40h] [rbp-19h] BYREF
  DWORD GrantedAccess; // [rsp+44h] [rbp-15h] BYREF
  WINBOOL AccessStatus; // [rsp+48h] [rbp-11h] BYREF
  DWORD PrivilegeSetLength; // [rsp+4Ch] [rbp-Dh] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-9h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+58h] [rbp-1h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+68h] [rbp+Fh] BYREF

  TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    if ( DesiredAccess && lpFileName )
    {
      v11 = TokenHandle;
      nLengthNeeded = 0;
      if ( GetFileSecurityW(lpFileName, 7u, 0, 0, &nLengthNeeded) || (v12 = GetLastError(), v6 = v12, v12 == 122) )
      {
        v6 = -2147024891;
        if ( nLengthNeeded )
        {
          v13 = operator new(nLengthNeeded + 1);
          if ( v13 )
          {
            if ( GetFileSecurityW(lpFileName, 7u, v13, nLengthNeeded, &nLengthNeeded) )
            {
              GenericMapping.GenericRead = 1179785;
              GenericMapping.GenericWrite = 1179926;
              GenericMapping.GenericExecute = 1179808;
              GenericMapping.GenericAll = 2032127;
              PrivilegeSetLength = 20;
              memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
              GrantedAccess = 0;
              AccessStatus = 0;
              if ( AccessCheck(
                     v13,
                     v11,
                     DesiredAccess,
                     &GenericMapping,
                     &PrivilegeSet,
                     &PrivilegeSetLength,
                     (LPDWORD)&AccessStatus,
                     (LPBOOL)&GrantedAccess)
                && GrantedAccess
                && (AccessStatus & DesiredAccess) == DesiredAccess )
              {
                v6 = 0;
              }
            }
            else
            {
              LastError = GetLastError();
              v6 = LastError;
              if ( LastError > 0 )
                v6 = (unsigned __int16)LastError | 0x80070000;
            }
            operator delete(v13);
          }
        }
      }
      else if ( v12 > 0 )
      {
        v6 = (unsigned __int16)v12 | 0x80070000;
      }
    }
    else
    {
      v6 = -2147024891;
    }
    goto LABEL_15;
  }
  result = GetLastError();
  if ( result == 1008 )
  {
    v6 = -2147024891;
    if ( ImpersonateSelf(SecurityImpersonation) )
    {
      v7 = GetCurrentThread();
      if ( OpenThreadToken(v7, 8u, 1, &TokenHandle) && DesiredAccess && lpFileName )
      {
        v8 = TokenHandle;
        nLengthNeeded = 0;
        if ( GetFileSecurityW(lpFileName, 7u, 0, 0, &nLengthNeeded) || (v9 = GetLastError(), v9 == 122) )
        {
          if ( nLengthNeeded )
          {
            v10 = operator new(nLengthNeeded + 1);
            if ( v10 )
            {
              if ( GetFileSecurityW(lpFileName, 7u, v10, nLengthNeeded, &nLengthNeeded) )
              {
                GenericMapping.GenericRead = 1179785;
                GenericMapping.GenericWrite = 1179926;
                GenericMapping.GenericExecute = 1179808;
                GenericMapping.GenericAll = 2032127;
                PrivilegeSetLength = 20;
                memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
                AccessStatus = 0;
                GrantedAccess = 0;
                if ( AccessCheck(
                       v10,
                       v8,
                       DesiredAccess,
                       &GenericMapping,
                       &PrivilegeSet,
                       &PrivilegeSetLength,
                       &GrantedAccess,
                       &AccessStatus)
                  && AccessStatus
                  && (GrantedAccess & DesiredAccess) == DesiredAccess )
                {
                  v6 = 0;
                }
              }
              else
              {
                v14 = GetLastError();
                v6 = v14;
                if ( v14 > 0 )
                  v6 = (unsigned __int16)v14 | 0x80070000;
              }
              operator delete(v10);
            }
          }
        }
        else if ( v9 > 0 )
        {
          v6 = (unsigned __int16)v9 | 0x80070000;
        }
        else
        {
          v6 = v9;
        }
      }
      RevertToSelf();
    }
LABEL_15:
    if ( TokenHandle != (void *)-1LL )
      CloseHandle(TokenHandle);
    return v6;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180002ab0  mov     [rsp-8+arg_10], rbx
0x180002ab5  mov     [rsp-8+arg_18], rsi
0x180002aba  push    rbp
0x180002abb  push    rdi
0x180002abc  push    r12
0x180002abe  push    r14
0x180002ac0  push    r15
0x180002ac2  lea     rbp, [rsp-37h]
0x180002ac7  sub     rsp, 90h
0x180002ace  mov     rax, cs:__security_cookie
0x180002ad5  xor     rax, rsp
0x180002ad8  mov     [rbp+57h+var_30], rax
0x180002adc  mov     r14d, edx
0x180002adf  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180002ae7  mov     rdi, rcx
0x180002aea  call    cs:__imp_GetCurrentThread
0x180002af0  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180002af4  mov     edx, 8; DesiredAccess
0x180002af9  mov     rcx, rax; ThreadHandle
0x180002afc  mov     r8d, 1; OpenAsSelf
0x180002b02  call    cs:__imp_OpenThreadToken
0x180002b08  test    eax, eax
0x180002b0a  jnz     loc_180002CAF
0x180002b10  call    cs:__imp_GetLastError
0x180002b16  cmp     eax, 3F0h
0x180002b1b  jnz     loc_180002E16
0x180002b21  mov     ecx, 2; ImpersonationLevel
0x180002b26  mov     ebx, 80070005h
0x180002b2b  call    cs:__imp_ImpersonateSelf
0x180002b31  test    eax, eax
0x180002b33  jz      loc_180002C75
0x180002b39  call    cs:__imp_GetCurrentThread
0x180002b3f  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180002b43  mov     edx, 8; DesiredAccess
0x180002b48  mov     rcx, rax; ThreadHandle
0x180002b4b  mov     r8d, 1; OpenAsSelf
0x180002b51  call    cs:__imp_OpenThreadToken
0x180002b57  test    eax, eax
0x180002b59  jz      loc_180002C6F
0x180002b5f  test    r14d, r14d
0x180002b62  jz      loc_180002C6F
0x180002b68  test    rdi, rdi
0x180002b6b  jz      loc_180002C6F
0x180002b71  mov     r12, [rbp+57h+TokenHandle]
0x180002b75  lea     rax, [rbp+57h+nLengthNeeded]
0x180002b79  xor     r15d, r15d
0x180002b7c  mov     [rsp+0B0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180002b81  xor     r9d, r9d; nLength
0x180002b84  mov     [rbp+57h+nLengthNeeded], r15d
0x180002b88  xor     r8d, r8d; pSecurityDescriptor
0x180002b8b  mov     edx, 7; RequestedInformation
0x180002b90  mov     rcx, rdi; lpFileName
0x180002b93  call    cs:__imp_GetFileSecurityW
0x180002b99  test    eax, eax
0x180002b9b  jnz     short loc_180002BAC
0x180002b9d  call    cs:__imp_GetLastError
0x180002ba3  cmp     eax, 7Ah ; 'z'
0x180002ba6  jnz     loc_180002E2B
0x180002bac  mov     eax, [rbp+57h+nLengthNeeded]
0x180002baf  test    eax, eax
0x180002bb1  jz      loc_180002C6F
0x180002bb7  lea     ecx, [rax+1]; Size
0x180002bba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002bbf  mov     rsi, rax
0x180002bc2  test    rax, rax
0x180002bc5  jz      loc_180002C6F
0x180002bcb  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x180002bcf  lea     rax, [rbp+57h+nLengthNeeded]
0x180002bd3  mov     r8, rsi; pSecurityDescriptor
0x180002bd6  mov     [rsp+0B0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180002bdb  mov     edx, 7; RequestedInformation
0x180002be0  mov     rcx, rdi; lpFileName
0x180002be3  call    cs:__imp_GetFileSecurityW
0x180002be9  test    eax, eax
0x180002beb  jz      loc_180002DCB
0x180002bf1  xor     eax, eax
0x180002bf3  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x180002bfa  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x180002bfd  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x180002c01  lea     rax, [rbp+57h+var_68]
0x180002c05  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x180002c0c  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x180002c11  xorps   xmm0, xmm0
0x180002c14  lea     rax, [rbp+57h+var_6C]
0x180002c18  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x180002c1f  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x180002c24  mov     r8d, r14d; DesiredAccess
0x180002c27  lea     rax, [rbp+57h+var_64]
0x180002c2b  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x180002c32  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180002c37  mov     rdx, r12; ClientToken
0x180002c3a  lea     rax, [rbp+57h+PrivilegeSet]
0x180002c3e  mov     [rbp+57h+var_64], 14h
0x180002c45  mov     rcx, rsi; pSecurityDescriptor
0x180002c48  mov     [rsp+0B0h+lpnLengthNeeded], rax; PrivilegeSet
0x180002c4d  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x180002c51  mov     [rbp+57h+var_68], r15d
0x180002c55  mov     [rbp+57h+var_6C], r15d
0x180002c59  call    cs:__imp_AccessCheck
0x180002c5f  test    eax, eax
0x180002c61  jnz     loc_180002E6F
0x180002c67  mov     rcx, rsi; Block
0x180002c6a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002c6f  call    cs:__imp_RevertToSelf
0x180002c75  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180002c79  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180002c7d  jz      short loc_180002C85
0x180002c7f  call    cs:__imp_CloseHandle
0x180002c85  mov     eax, ebx
0x180002c87  mov     rcx, [rbp+57h+var_30]
0x180002c8b  xor     rcx, rsp; StackCookie
0x180002c8e  call    __security_check_cookie
0x180002c93  lea     r11, [rsp+0B0h+var_20]
0x180002c9b  mov     rbx, [r11+40h]
0x180002c9f  mov     rsi, [r11+48h]
0x180002ca3  mov     rsp, r11
0x180002ca6  pop     r15
0x180002ca8  pop     r14
0x180002caa  pop     r12
0x180002cac  pop     rdi
0x180002cad  pop     rbp
0x180002cae  retn
0x180002caf  test    r14d, r14d
0x180002cb2  jz      loc_180002E65
0x180002cb8  test    rdi, rdi
0x180002cbb  jz      loc_180002E65
0x180002cc1  mov     r12, [rbp+57h+TokenHandle]
0x180002cc5  lea     rax, [rbp+57h+nLengthNeeded]
0x180002cc9  xor     r15d, r15d
0x180002ccc  mov     [rsp+0B0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180002cd1  xor     r9d, r9d; nLength
0x180002cd4  mov     [rbp+57h+nLengthNeeded], r15d
0x180002cd8  xor     r8d, r8d; pSecurityDescriptor
0x180002cdb  mov     edx, 7; RequestedInformation
0x180002ce0  mov     rcx, rdi; lpFileName
0x180002ce3  call    cs:__imp_GetFileSecurityW
0x180002ce9  test    eax, eax
0x180002ceb  jnz     short loc_180002CFE
0x180002ced  call    cs:__imp_GetLastError
0x180002cf3  mov     ebx, eax
0x180002cf5  cmp     eax, 7Ah ; 'z'
0x180002cf8  jnz     loc_180002E00
0x180002cfe  mov     eax, [rbp+57h+nLengthNeeded]
0x180002d01  mov     ebx, 80070005h
0x180002d06  test    eax, eax
0x180002d08  jz      loc_180002C75
0x180002d0e  lea     ecx, [rax+1]; Size
0x180002d11  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002d16  mov     rsi, rax
0x180002d19  test    rax, rax
0x180002d1c  jz      loc_180002C75
0x180002d22  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x180002d26  lea     rax, [rbp+57h+nLengthNeeded]
0x180002d2a  mov     r8, rsi; pSecurityDescriptor
0x180002d2d  mov     [rsp+0B0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180002d32  mov     edx, 7; RequestedInformation
0x180002d37  mov     rcx, rdi; lpFileName
0x180002d3a  call    cs:__imp_GetFileSecurityW
0x180002d40  test    eax, eax
0x180002d42  jz      loc_180002DE9
0x180002d48  xor     eax, eax
0x180002d4a  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x180002d51  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x180002d54  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x180002d58  lea     rax, [rbp+57h+var_6C]
0x180002d5c  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x180002d63  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x180002d68  xorps   xmm0, xmm0
0x180002d6b  lea     rax, [rbp+57h+var_68]
0x180002d6f  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x180002d76  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x180002d7b  mov     r8d, r14d; DesiredAccess
0x180002d7e  lea     rax, [rbp+57h+var_64]
0x180002d82  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x180002d89  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180002d8e  mov     rdx, r12; ClientToken
0x180002d91  lea     rax, [rbp+57h+PrivilegeSet]
0x180002d95  mov     [rbp+57h+var_64], 14h
0x180002d9c  mov     rcx, rsi; pSecurityDescriptor
0x180002d9f  mov     [rsp+0B0h+lpnLengthNeeded], rax; PrivilegeSet
0x180002da4  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x180002da8  mov     [rbp+57h+var_6C], r15d
0x180002dac  mov     [rbp+57h+var_68], r15d
0x180002db0  call    cs:__imp_AccessCheck
0x180002db6  test    eax, eax
0x180002db8  jnz     loc_180002E44
0x180002dbe  mov     rcx, rsi; Block
0x180002dc1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002dc6  jmp     loc_180002C75
0x180002dcb  call    cs:__imp_GetLastError
0x180002dd1  mov     ebx, eax
0x180002dd3  test    eax, eax
0x180002dd5  jle     loc_180002C67
0x180002ddb  movzx   ebx, ax
0x180002dde  or      ebx, 80070000h
0x180002de4  jmp     loc_180002C67
0x180002de9  call    cs:__imp_GetLastError
0x180002def  mov     ebx, eax
0x180002df1  test    eax, eax
0x180002df3  jle     short loc_180002DBE
0x180002df5  movzx   ebx, ax
0x180002df8  or      ebx, 80070000h
0x180002dfe  jmp     short loc_180002DBE
0x180002e00  test    eax, eax
0x180002e02  jle     loc_180002C75
0x180002e08  movzx   ebx, ax
0x180002e0b  or      ebx, 80070000h
0x180002e11  jmp     loc_180002C75
0x180002e16  test    eax, eax
0x180002e18  jle     loc_180002C87
0x180002e1e  movzx   eax, ax
0x180002e21  or      eax, 80070000h
0x180002e26  jmp     loc_180002C87
0x180002e2b  test    eax, eax
0x180002e2d  jg      short loc_180002E36
0x180002e2f  mov     ebx, eax
0x180002e31  jmp     loc_180002C6F
0x180002e36  movzx   ebx, ax
0x180002e39  or      ebx, 80070000h
0x180002e3f  jmp     loc_180002C6F
0x180002e44  cmp     [rbp+57h+var_6C], r15d
0x180002e48  jz      loc_180002DBE
0x180002e4e  mov     eax, r14d
0x180002e51  and     eax, [rbp+57h+var_68]
0x180002e54  cmp     eax, r14d
0x180002e57  jnz     loc_180002DBE
0x180002e5d  mov     ebx, r15d
0x180002e60  jmp     loc_180002DBE
0x180002e65  mov     ebx, 80070005h
0x180002e6a  jmp     loc_180002C75
0x180002e6f  cmp     [rbp+57h+var_68], r15d
0x180002e73  jz      loc_180002C67
0x180002e79  mov     eax, r14d
0x180002e7c  and     eax, [rbp+57h+var_6C]
0x180002e7f  cmp     eax, r14d
0x180002e82  jnz     loc_180002C67
0x180002e88  mov     ebx, r15d
0x180002e8b  jmp     loc_180002C67
```
