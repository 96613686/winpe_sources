# UtilIsLowRightsToken(void *)

- ea: `0x18000e330`
- end: `0x18000e432`
- name: `?UtilIsLowRightsToken@@YAJPEAX@Z`
- size: `258`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e7c0`
- `0x18003c344`

## callees

- `0x180002890`
- `0x180003474`
- `0x18000e330`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e3d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e3d2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e387`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e3c8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e387`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e3c8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000e3f6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000e3f6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000e406`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000e406`

## pseudocode

```c
signed int __fastcall UtilIsLowRightsToken(HANDLE TokenHandle)
{
  signed int LastError; // eax
  bool v3; // zf
  signed int result; // eax
  PUCHAR SidSubAuthorityCount; // rax
  int TokenInformation; // [rsp+30h] [rbp-88h] BYREF
  DWORD ReturnLength; // [rsp+34h] [rbp-84h] BYREF
  DWORD v8; // [rsp+38h] [rbp-80h] BYREF
  PSID pSid[12]; // [rsp+40h] [rbp-78h] BYREF

  memset_0(pSid, 0, 0x58u);
  TokenInformation = 0;
  ReturnLength = 4;
  if ( !GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
  {
    LastError = GetLastError();
    v3 = LastError == 0;
    if ( LastError > 0 )
      v3 = 0;
    if ( !v3 )
      goto LABEL_5;
    return 0;
  }
  if ( TokenInformation )
    return 0;
LABEL_5:
  v8 = 84;
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, pSid, 0x54u, &v8) )
  {
    SidSubAuthorityCount = GetSidSubAuthorityCount(pSid[0]);
    return *GetSidSubAuthority(pSid[0], (unsigned int)*SidSubAuthorityCount - 1) >= 0x2000;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000e330  push    rbx
0x18000e332  sub     rsp, 0B0h
0x18000e339  mov     rax, cs:__security_cookie
0x18000e340  xor     rax, rsp
0x18000e343  mov     [rsp+0B8h+var_18], rax
0x18000e34b  xor     edx, edx; Val
0x18000e34d  mov     rbx, rcx
0x18000e350  lea     rcx, [rsp+0B8h+pSid]; void *
0x18000e355  lea     r8d, [rdx+58h]; Size
0x18000e359  call    memset_0
0x18000e35e  mov     r9d, 4; TokenInformationLength
0x18000e364  mov     [rsp+0B8h+TokenInformation], 0
0x18000e36c  lea     rax, [rsp+0B8h+var_84]
0x18000e371  mov     [rsp+0B8h+var_84], r9d
0x18000e376  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x18000e37b  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18000e380  mov     rcx, rbx; TokenHandle
0x18000e383  lea     edx, [r9+19h]; TokenInformationClass
0x18000e387  call    cs:__imp_GetTokenInformation
0x18000e38d  test    eax, eax
0x18000e38f  jnz     short loc_18000E3E6
0x18000e391  call    cs:__imp_GetLastError
0x18000e397  test    eax, eax
0x18000e399  jle     short loc_18000E3A5
0x18000e39b  movzx   eax, ax
0x18000e39e  or      eax, 80070000h
0x18000e3a3  test    eax, eax
0x18000e3a5  jz      short loc_18000E3ED
0x18000e3a7  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18000e3ad  lea     rax, [rsp+0B8h+var_80]
0x18000e3b2  lea     r8, [rsp+0B8h+pSid]; TokenInformation
0x18000e3b7  mov     [rsp+0B8h+var_80], r9d
0x18000e3bc  mov     rcx, rbx; TokenHandle
0x18000e3bf  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18000e3c4  lea     edx, [r9-3Bh]; TokenInformationClass
0x18000e3c8  call    cs:__imp_GetTokenInformation
0x18000e3ce  test    eax, eax
0x18000e3d0  jnz     short loc_18000E3F1
0x18000e3d2  call    cs:__imp_GetLastError
0x18000e3d8  test    eax, eax
0x18000e3da  jle     short loc_18000E419
0x18000e3dc  movzx   eax, ax
0x18000e3df  or      eax, 80070000h
0x18000e3e4  jmp     short loc_18000E419
0x18000e3e6  cmp     [rsp+0B8h+TokenInformation], 0
0x18000e3eb  jz      short loc_18000E3A7
0x18000e3ed  xor     eax, eax
0x18000e3ef  jmp     short loc_18000E419
0x18000e3f1  mov     rcx, [rsp+0B8h+pSid]; pSid
0x18000e3f6  call    cs:__imp_GetSidSubAuthorityCount
0x18000e3fc  mov     rcx, [rsp+0B8h+pSid]; pSid
0x18000e401  movzx   edx, byte ptr [rax]
0x18000e404  dec     edx; nSubAuthority
0x18000e406  call    cs:__imp_GetSidSubAuthority
0x18000e40c  xor     ecx, ecx
0x18000e40e  cmp     dword ptr [rax], 2000h
0x18000e414  setnb   cl
0x18000e417  mov     eax, ecx
0x18000e419  mov     rcx, [rsp+0B8h+var_18]
0x18000e421  xor     rcx, rsp; StackCookie
0x18000e424  call    __security_check_cookie
0x18000e429  add     rsp, 0B0h
0x18000e430  pop     rbx
0x18000e431  retn
```
