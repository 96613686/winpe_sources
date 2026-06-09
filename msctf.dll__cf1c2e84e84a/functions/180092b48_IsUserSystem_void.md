# IsUserSystem(void)

- ea: `0x180092b48`
- end: `0x180092c9a`
- name: `?IsUserSystem@@YA_NXZ`
- size: `338`
- prototype: `bool(void)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180053a08`
- `0x18008cb18`
- `0x1800d5148`
- `0x1800d5b30`

## callees

- `0x1800139a4`
- `0x180092b48`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092bc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092bc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180092b7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180092b7d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180092b8f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180092b8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180092c6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180092c6d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180092be2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180092be2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180092bbb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180092c09`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180092bbb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180092c09`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180092c4e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180092c4e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180092c3b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180092c3b`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180092c2b`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180092c2b`

## pseudocode

```c
bool IsUserSystem(void)
{
  HANDLE CurrentProcess; // rax
  PSID *v1; // rbx
  DWORD TokenInformationLength; // [rsp+30h] [rbp-29h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-21h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+40h] [rbp-19h] BYREF
  _BYTE Sid[80]; // [rsp+50h] [rbp-9h] BYREF

  if ( dword_18013DF18 == -1 )
  {
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      TokenInformationLength = 0;
      GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
      if ( GetLastError() == 122 )
      {
        if ( TokenInformationLength )
        {
          v1 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
          if ( v1 )
          {
            if ( GetTokenInformation(TokenHandle, TokenUser, v1, TokenInformationLength, &TokenInformationLength) )
            {
              *(_DWORD *)pIdentifierAuthority.Value = 0;
              *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
              if ( InitializeSid(Sid, &pIdentifierAuthority, 1u) )
              {
                *GetSidSubAuthority(Sid, 0) = 18;
                dword_18013DF18 = EqualSid(*v1, Sid);
              }
            }
            cicMemFree(v1);
          }
        }
      }
      CloseHandle(TokenHandle);
    }
  }
  return dword_18013DF18 == 1;
}

```

## disassembly

```asm
0x180092b48  mov     [rsp-8+arg_0], rbx
0x180092b4d  push    rbp
0x180092b4e  lea     rbp, [rsp-57h]
0x180092b53  sub     rsp, 0B0h
0x180092b5a  mov     rax, cs:__security_cookie
0x180092b61  xor     rax, rsp
0x180092b64  mov     [rbp+57h+var_10], rax
0x180092b68  cmp     cs:dword_18013DF18, 0FFFFFFFFh
0x180092b6f  jnz     loc_180092C73
0x180092b75  mov     [rbp+57h+TokenHandle], 0
0x180092b7d  call    cs:__imp_GetCurrentProcess
0x180092b83  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180092b87  mov     edx, 8; DesiredAccess
0x180092b8c  mov     rcx, rax; ProcessHandle
0x180092b8f  call    cs:__imp_OpenProcessToken
0x180092b95  test    eax, eax
0x180092b97  jz      loc_180092C73
0x180092b9d  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180092ba1  lea     rax, [rbp+57h+TokenInformationLength]
0x180092ba5  xor     r9d, r9d; TokenInformationLength
0x180092ba8  mov     [rbp+57h+TokenInformationLength], 0
0x180092baf  xor     r8d, r8d; TokenInformation
0x180092bb2  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180092bb7  lea     edx, [r9+1]; TokenInformationClass
0x180092bbb  call    cs:__imp_GetTokenInformation
0x180092bc1  call    cs:__imp_GetLastError
0x180092bc7  cmp     eax, 7Ah ; 'z'
0x180092bca  jnz     loc_180092C69
0x180092bd0  mov     eax, [rbp+57h+TokenInformationLength]
0x180092bd3  test    eax, eax
0x180092bd5  jz      loc_180092C69
0x180092bdb  mov     edx, eax; uBytes
0x180092bdd  mov     ecx, 40h ; '@'; uFlags
0x180092be2  call    cs:__imp_LocalAlloc
0x180092be8  mov     rbx, rax
0x180092beb  test    rax, rax
0x180092bee  jz      short loc_180092C69
0x180092bf0  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180092bf4  lea     rax, [rbp+57h+TokenInformationLength]
0x180092bf8  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180092bfc  mov     r8, rbx; TokenInformation
0x180092bff  mov     edx, 1; TokenInformationClass
0x180092c04  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180092c09  call    cs:__imp_GetTokenInformation
0x180092c0f  test    eax, eax
0x180092c11  jz      short loc_180092C61
0x180092c13  mov     r8b, 1; nSubAuthorityCount
0x180092c16  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], 0
0x180092c1d  lea     rdx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180092c21  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180092c27  lea     rcx, [rbp+57h+Sid]; Sid
0x180092c2b  call    cs:__imp_InitializeSid
0x180092c31  test    eax, eax
0x180092c33  jz      short loc_180092C61
0x180092c35  xor     edx, edx; nSubAuthority
0x180092c37  lea     rcx, [rbp+57h+Sid]; pSid
0x180092c3b  call    cs:__imp_GetSidSubAuthority
0x180092c41  lea     rdx, [rbp+57h+Sid]; pSid2
0x180092c45  mov     dword ptr [rax], 12h
0x180092c4b  mov     rcx, [rbx]; pSid1
0x180092c4e  call    cs:__imp_EqualSid
0x180092c54  xor     ecx, ecx
0x180092c56  test    eax, eax
0x180092c58  setnz   cl
0x180092c5b  mov     cs:dword_18013DF18, ecx
0x180092c61  mov     rcx, rbx
0x180092c64  call    cicMemFree
0x180092c69  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180092c6d  call    cs:__imp_CloseHandle
0x180092c73  cmp     cs:dword_18013DF18, 1
0x180092c7a  setz    al
0x180092c7d  mov     rcx, [rbp+57h+var_10]
0x180092c81  xor     rcx, rsp; StackCookie
0x180092c84  call    __security_check_cookie
0x180092c89  mov     rbx, [rsp+0B0h+arg_0]
0x180092c91  add     rsp, 0B0h
0x180092c98  pop     rbp
0x180092c99  retn
```
