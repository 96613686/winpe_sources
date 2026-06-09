# IESetTokenIntegrityLevel(void *,ulong)

- ea: `0x180064ca4`
- end: `0x180064da4`
- name: `?IESetTokenIntegrityLevel@@YAHPEAXK@Z`
- size: `256`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180064b70`

## callees

- `0x180064ca4`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064d82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064d82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064d7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064d7a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180064ce7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180064ce7`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180064cd7`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180064d34`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180064cd7`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180064d34`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180064d65`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180064d65`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180064d45`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180064d45`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064d26`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064d26`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180064d08`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180064d08`

## pseudocode

```c
_BOOL8 __fastcall IESetTokenIntegrityLevel(HANDLE TokenHandle)
{
  PSID *v2; // rax
  PSID *v3; // rdi
  DWORD LastError; // ebx
  DWORD TokenInformationLength; // [rsp+30h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+34h] [rbp-24h] BYREF

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
  TokenInformationLength = GetSidLengthRequired(1u) + 16;
  v2 = (PSID *)LocalAlloc(0, TokenInformationLength);
  v3 = v2;
  if ( v2 )
  {
    *v2 = v2 + 2;
    InitializeSid(v2 + 2, &pIdentifierAuthority, 1u);
    if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, v3, TokenInformationLength, &TokenInformationLength)
      || (LastError = 0,
          TokenInformationLength = GetSidLengthRequired(1u) + 16,
          *GetSidSubAuthority(*v3, 0) = 4096,
          *((_DWORD *)v3 + 2) = 96,
          !SetTokenInformation(TokenHandle, TokenIntegrityLevel, v3, TokenInformationLength)) )
    {
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = 8;
  }
  LocalFree(v3);
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180064ca4  push    rbp
0x180064ca6  push    rbx
0x180064ca7  push    rsi
0x180064ca8  push    rdi
0x180064ca9  mov     rbp, rsp
0x180064cac  sub     rsp, 58h
0x180064cb0  mov     rax, cs:__security_cookie
0x180064cb7  xor     rax, rsp
0x180064cba  mov     [rbp+var_18], rax
0x180064cbe  mov     rsi, rcx
0x180064cc1  mov     [rbp+TokenInformationLength], 0
0x180064cc8  mov     cl, 1; nSubAuthorityCount
0x180064cca  mov     dword ptr [rbp+pIdentifierAuthority.Value], 0
0x180064cd1  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 1000h
0x180064cd7  call    cs:__imp_GetSidLengthRequired
0x180064cdd  add     eax, 10h
0x180064ce0  xor     ecx, ecx; uFlags
0x180064ce2  mov     edx, eax; uBytes
0x180064ce4  mov     [rbp+TokenInformationLength], eax
0x180064ce7  call    cs:__imp_LocalAlloc
0x180064ced  mov     rdi, rax
0x180064cf0  test    rax, rax
0x180064cf3  jnz     short loc_180064CFA
0x180064cf5  lea     ebx, [rax+8]
0x180064cf8  jmp     short loc_180064D77
0x180064cfa  lea     rcx, [rax+10h]; Sid
0x180064cfe  mov     r8b, 1; nSubAuthorityCount
0x180064d01  lea     rdx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180064d05  mov     [rax], rcx
0x180064d08  call    cs:__imp_InitializeSid
0x180064d0e  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180064d12  lea     rax, [rbp+TokenInformationLength]
0x180064d16  mov     r8, rdi; TokenInformation
0x180064d19  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180064d1e  mov     edx, 19h; TokenInformationClass
0x180064d23  mov     rcx, rsi; TokenHandle
0x180064d26  call    cs:__imp_GetTokenInformation
0x180064d2c  test    eax, eax
0x180064d2e  jz      short loc_180064D6F
0x180064d30  mov     cl, 1; nSubAuthorityCount
0x180064d32  xor     ebx, ebx
0x180064d34  call    cs:__imp_GetSidLengthRequired
0x180064d3a  add     eax, 10h
0x180064d3d  xor     edx, edx; nSubAuthority
0x180064d3f  mov     [rbp+TokenInformationLength], eax
0x180064d42  mov     rcx, [rdi]; pSid
0x180064d45  call    cs:__imp_GetSidSubAuthority
0x180064d4b  mov     r8, rdi; TokenInformation
0x180064d4e  lea     edx, [rbx+19h]; TokenInformationClass
0x180064d51  mov     rcx, rsi; TokenHandle
0x180064d54  mov     dword ptr [rax], 1000h
0x180064d5a  mov     dword ptr [rdi+8], 60h ; '`'
0x180064d61  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180064d65  call    cs:__imp_SetTokenInformation
0x180064d6b  test    eax, eax
0x180064d6d  jnz     short loc_180064D77
0x180064d6f  call    cs:__imp_GetLastError
0x180064d75  mov     ebx, eax
0x180064d77  mov     rcx, rdi; hMem
0x180064d7a  call    cs:__imp_LocalFree
0x180064d80  mov     ecx, ebx; dwErrCode
0x180064d82  call    cs:__imp_SetLastError
0x180064d88  xor     eax, eax
0x180064d8a  test    ebx, ebx
0x180064d8c  setz    al
0x180064d8f  mov     rcx, [rbp+var_18]
0x180064d93  xor     rcx, rsp; StackCookie
0x180064d96  call    __security_check_cookie
0x180064d9b  add     rsp, 58h
0x180064d9f  pop     rdi
0x180064da0  pop     rsi
0x180064da1  pop     rbx
0x180064da2  pop     rbp
0x180064da3  retn
```
