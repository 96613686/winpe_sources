# CEfsTokenManager::CheckIsLowILToken(void *,int *)

- ea: `0x18000c264`
- end: `0x18000c3d5`
- name: `?CheckIsLowILToken@CEfsTokenManager@@SAKPEAXPEAH@Z`
- size: `369`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c108`

## callees

- `0x1800037b8`
- `0x18000c264`
- `0x18000c3dc`
- `0x18000c430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c347`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c294`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c337`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c294`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c337`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000c365`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000c365`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000c379`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000c379`

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
0x18000c264  mov     rax, rsp
0x18000c267  mov     [rax+8], rbx
0x18000c26b  push    rsi
0x18000c26c  push    rdi
0x18000c26d  push    r14
0x18000c26f  sub     rsp, 30h
0x18000c273  xor     edi, edi
0x18000c275  mov     r14, rdx
0x18000c278  mov     [rax+20h], rdi
0x18000c27c  xor     r9d, r9d; TokenInformationLength
0x18000c27f  mov     [rax+18h], edi
0x18000c282  lea     rax, [rax+18h]
0x18000c286  xor     r8d, r8d; TokenInformation
0x18000c289  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000c28e  lea     edx, [rdi+19h]; TokenInformationClass
0x18000c291  mov     rsi, rcx
0x18000c294  call    cs:__imp_GetTokenInformation
0x18000c29b  nop     dword ptr [rax+rax+00h]
0x18000c2a0  test    eax, eax
0x18000c2a2  jnz     loc_18000C395
0x18000c2a8  call    cs:__imp_GetLastError
0x18000c2af  nop     dword ptr [rax+rax+00h]
0x18000c2b4  mov     ebx, eax
0x18000c2b6  cmp     eax, 7Ah ; 'z'
0x18000c2b9  jz      short loc_18000C2DB
0x18000c2bb  lea     r9d, [rdi+1Dh]
0x18000c2bf  mov     dword ptr [rsp+48h+ReturnLength], 15Ch
0x18000c2c7  mov     r8d, eax
0x18000c2ca  lea     rdx, EFS_API_ERROR
0x18000c2d1  call    fnEfsLogTrace1
0x18000c2d6  jmp     loc_18000C3C4
0x18000c2db  mov     ecx, [rsp+48h+TokenInformationLength]; dwBytes
0x18000c2df  lea     rdx, [rsp+48h+TokenInformation]; void **
0x18000c2e4  call    ?EfsxLibAllocZero@@YAK_KPEAPEAX@Z; EfsxLibAllocZero(unsigned __int64,void * *)
0x18000c2e9  mov     ebx, eax
0x18000c2eb  test    eax, eax
0x18000c2ed  jz      short loc_18000C318
0x18000c2ef  mov     r8d, [rsp+48h+TokenInformationLength]
0x18000c2f4  lea     rdx, EFS_ERROR_MEMORY
0x18000c2fb  mov     r9d, 1Dh
0x18000c301  mov     dword ptr [rsp+48h+ReturnLength], 16Ch
0x18000c309  call    fnEfsLogTrace1
0x18000c30e  mov     rdi, [rsp+48h+TokenInformation]
0x18000c313  jmp     loc_18000C3B7
0x18000c318  mov     rdi, [rsp+48h+TokenInformation]
0x18000c31d  lea     rax, [rsp+48h+TokenInformationLength]
0x18000c322  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18000c327  mov     r8, rdi; TokenInformation
0x18000c32a  mov     edx, 19h; TokenInformationClass
0x18000c32f  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000c334  mov     rcx, rsi; TokenHandle
0x18000c337  call    cs:__imp_GetTokenInformation
0x18000c33e  nop     dword ptr [rax+rax+00h]
0x18000c343  test    eax, eax
0x18000c345  jnz     short loc_18000C362
0x18000c347  call    cs:__imp_GetLastError
0x18000c34e  nop     dword ptr [rax+rax+00h]
0x18000c353  mov     ebx, eax
0x18000c355  mov     dword ptr [rsp+48h+ReturnLength], 174h
0x18000c35d  mov     r8d, eax
0x18000c360  jmp     short loc_18000C3A5
0x18000c362  mov     rcx, [rdi]; pSid
0x18000c365  call    cs:__imp_GetSidSubAuthorityCount
0x18000c36c  nop     dword ptr [rax+rax+00h]
0x18000c371  mov     rcx, [rdi]; pSid
0x18000c374  movzx   edx, byte ptr [rax]
0x18000c377  dec     edx; nSubAuthority
0x18000c379  call    cs:__imp_GetSidSubAuthority
0x18000c380  nop     dword ptr [rax+rax+00h]
0x18000c385  xor     ecx, ecx
0x18000c387  cmp     dword ptr [rax], 2000h
0x18000c38d  setb    cl
0x18000c390  mov     [r14], ecx
0x18000c393  jmp     short loc_18000C3B7
0x18000c395  mov     ebx, 6Fh ; 'o'
0x18000c39a  mov     dword ptr [rsp+48h+ReturnLength], 165h
0x18000c3a2  mov     r8d, ebx
0x18000c3a5  mov     r9d, 1Dh
0x18000c3ab  lea     rdx, EFS_API_ERROR
0x18000c3b2  call    fnEfsLogTrace1
0x18000c3b7  test    rdi, rdi
0x18000c3ba  jz      short loc_18000C3C4
0x18000c3bc  mov     rcx, rdi; lpMem
0x18000c3bf  call    ?EfsxLibFree@@YAXPEAX@Z; EfsxLibFree(void *)
0x18000c3c4  mov     eax, ebx
0x18000c3c6  mov     rbx, [rsp+48h+arg_0]
0x18000c3cb  add     rsp, 30h
0x18000c3cf  pop     r14
0x18000c3d1  pop     rdi
0x18000c3d2  pop     rsi
0x18000c3d3  retn
```
