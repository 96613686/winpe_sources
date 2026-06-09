# CEfsTokenManager::CheckIsLowILToken(void *,int *)

- ea: `0x18000b614`
- end: `0x18000b760`
- name: `?CheckIsLowILToken@CEfsTokenManager@@SAKPEAXPEAH@Z`
- size: `332`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b4e4`

## callees

- `0x180003604`
- `0x18000b614`
- `0x18000b768`
- `0x18000b7ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6e5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b644`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b6db`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b644`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b6db`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000b6fd`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000b6fd`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000b70b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000b70b`

## pseudocode

```c
__int64 __fastcall CEfsTokenManager::CheckIsLowILToken(HANDLE TokenHandle, int *a2)
{
  PSID *v2; // rdi
  int v5; // ecx
  DWORD LastError; // eax
  int v7; // ecx
  DWORD v8; // ebx
  int v9; // ecx
  int v10; // ecx
  PUCHAR SidSubAuthorityCount; // rax
  DWORD TokenInformationLength; // [rsp+60h] [rbp+18h] BYREF
  LPVOID TokenInformation; // [rsp+68h] [rbp+20h] BYREF

  v2 = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) )
  {
    v8 = 111;
    fnEfsLogTrace1(v5, (unsigned int)EFS_API_ERROR, 111, 29, 101);
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError != 122 )
    {
      fnEfsLogTrace1(v7, (unsigned int)EFS_API_ERROR, LastError, 29, 92);
      return v8;
    }
    v8 = EfsxLibAllocZero(TokenInformationLength, &TokenInformation);
    if ( v8 )
    {
      fnEfsLogTrace1(v9, (unsigned int)EFS_ERROR_MEMORY, TokenInformationLength, 29, 108);
      v2 = (PSID *)TokenInformation;
    }
    else
    {
      v2 = (PSID *)TokenInformation;
      if ( GetTokenInformation(
             TokenHandle,
             TokenIntegrityLevel,
             TokenInformation,
             TokenInformationLength,
             &TokenInformationLength) )
      {
        SidSubAuthorityCount = GetSidSubAuthorityCount(*v2);
        *a2 = *GetSidSubAuthority(*v2, (unsigned int)*SidSubAuthorityCount - 1) < 0x2000;
      }
      else
      {
        v8 = GetLastError();
        fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, v8, 29, 116);
      }
    }
  }
  if ( v2 )
    EfsxLibFree(v2);
  return v8;
}

```

## disassembly

```asm
0x18000b614  mov     rax, rsp
0x18000b617  mov     [rax+8], rbx
0x18000b61b  push    rsi
0x18000b61c  push    rdi
0x18000b61d  push    r14
0x18000b61f  sub     rsp, 30h
0x18000b623  xor     edi, edi
0x18000b625  mov     r14, rdx
0x18000b628  mov     [rax+20h], rdi
0x18000b62c  xor     r9d, r9d; TokenInformationLength
0x18000b62f  mov     [rax+18h], edi
0x18000b632  lea     rax, [rax+18h]
0x18000b636  xor     r8d, r8d; TokenInformation
0x18000b639  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000b63e  lea     edx, [rdi+19h]; TokenInformationClass
0x18000b641  mov     rsi, rcx
0x18000b644  call    cs:__imp_GetTokenInformation
0x18000b64a  test    eax, eax
0x18000b64c  jnz     loc_18000B721
0x18000b652  call    cs:__imp_GetLastError
0x18000b658  mov     ebx, eax
0x18000b65a  cmp     eax, 7Ah ; 'z'
0x18000b65d  jz      short loc_18000B67F
0x18000b65f  lea     r9d, [rdi+1Dh]
0x18000b663  mov     dword ptr [rsp+48h+ReturnLength], 15Ch
0x18000b66b  mov     r8d, eax
0x18000b66e  lea     rdx, EFS_API_ERROR
0x18000b675  call    fnEfsLogTrace1
0x18000b67a  jmp     loc_18000B750
0x18000b67f  mov     ecx, [rsp+48h+TokenInformationLength]; dwBytes
0x18000b683  lea     rdx, [rsp+48h+TokenInformation]; void **
0x18000b688  call    ?EfsxLibAllocZero@@YAK_KPEAPEAX@Z; EfsxLibAllocZero(unsigned __int64,void * *)
0x18000b68d  mov     ebx, eax
0x18000b68f  test    eax, eax
0x18000b691  jz      short loc_18000B6BC
0x18000b693  mov     r8d, [rsp+48h+TokenInformationLength]
0x18000b698  lea     rdx, EFS_ERROR_MEMORY
0x18000b69f  mov     r9d, 1Dh
0x18000b6a5  mov     dword ptr [rsp+48h+ReturnLength], 16Ch
0x18000b6ad  call    fnEfsLogTrace1
0x18000b6b2  mov     rdi, [rsp+48h+TokenInformation]
0x18000b6b7  jmp     loc_18000B743
0x18000b6bc  mov     rdi, [rsp+48h+TokenInformation]
0x18000b6c1  lea     rax, [rsp+48h+TokenInformationLength]
0x18000b6c6  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18000b6cb  mov     r8, rdi; TokenInformation
0x18000b6ce  mov     edx, 19h; TokenInformationClass
0x18000b6d3  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000b6d8  mov     rcx, rsi; TokenHandle
0x18000b6db  call    cs:__imp_GetTokenInformation
0x18000b6e1  test    eax, eax
0x18000b6e3  jnz     short loc_18000B6FA
0x18000b6e5  call    cs:__imp_GetLastError
0x18000b6eb  mov     ebx, eax
0x18000b6ed  mov     dword ptr [rsp+48h+ReturnLength], 174h
0x18000b6f5  mov     r8d, eax
0x18000b6f8  jmp     short loc_18000B731
0x18000b6fa  mov     rcx, [rdi]; pSid
0x18000b6fd  call    cs:__imp_GetSidSubAuthorityCount
0x18000b703  mov     rcx, [rdi]; pSid
0x18000b706  movzx   edx, byte ptr [rax]
0x18000b709  dec     edx; nSubAuthority
0x18000b70b  call    cs:__imp_GetSidSubAuthority
0x18000b711  xor     ecx, ecx
0x18000b713  cmp     dword ptr [rax], 2000h
0x18000b719  setb    cl
0x18000b71c  mov     [r14], ecx
0x18000b71f  jmp     short loc_18000B743
0x18000b721  mov     ebx, 6Fh ; 'o'
0x18000b726  mov     dword ptr [rsp+48h+ReturnLength], 165h
0x18000b72e  mov     r8d, ebx
0x18000b731  mov     r9d, 1Dh
0x18000b737  lea     rdx, EFS_API_ERROR
0x18000b73e  call    fnEfsLogTrace1
0x18000b743  test    rdi, rdi
0x18000b746  jz      short loc_18000B750
0x18000b748  mov     rcx, rdi; lpMem
0x18000b74b  call    ?EfsxLibFree@@YAXPEAX@Z; EfsxLibFree(void *)
0x18000b750  mov     eax, ebx
0x18000b752  mov     rbx, [rsp+48h+arg_0]
0x18000b757  add     rsp, 30h
0x18000b75b  pop     r14
0x18000b75d  pop     rdi
0x18000b75e  pop     rsi
0x18000b75f  retn
```
