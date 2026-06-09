# GetTokenId(void *)

- ea: `0x180006760`
- end: `0x18000689d`
- name: `?GetTokenId@@YAPEAU_CUCS_TOKEN_ID@@PEAX@Z`
- size: `317`
- prototype: `struct _CUCS_TOKEN_ID *__fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005700`

## callees

- `0x180006760`
- `0x1800068b0`
- `0x180008330`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000688a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000688a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800067c3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800067c3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000678c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800067f3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006843`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006879`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000678c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800067f3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006843`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006879`

## pseudocode

```c
struct _CUCS_TOKEN_ID *__fastcall GetTokenId(HANDLE TokenHandle)
{
  _QWORD *v1; // rbx
  __int64 v3; // rsi
  DWORD v4; // ecx
  _QWORD *v5; // rax
  char *v7; // r8
  DWORD ReturnLength; // [rsp+58h] [rbp+10h] BYREF
  DWORD TokenInformationLength; // [rsp+60h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  ReturnLength = 0;
  v1 = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( TokenInformationLength )
  {
    v3 = (TokenInformationLength + 7) & 0xFFFFFFF8;
    if ( (unsigned int)I_CryptIsAppContainerToken(TokenHandle) )
    {
      GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &ReturnLength);
      v4 = ReturnLength;
      if ( !ReturnLength )
        return (struct _CUCS_TOKEN_ID *)v1;
    }
    else
    {
      v4 = ReturnLength;
    }
    v5 = LocalAlloc(0x40u, v4 + (_DWORD)v3 + 16);
    v1 = v5;
    if ( v5 )
    {
      *v5 = v5 + 2;
      if ( !GetTokenInformation(TokenHandle, TokenUser, v5 + 2, TokenInformationLength, &TokenInformationLength)
        || ReturnLength
        && (v7 = (char *)v1 + v3 + 16,
            v1[1] = v7,
            !GetTokenInformation(TokenHandle, TokenAppContainerSid, v7, ReturnLength, &ReturnLength)) )
      {
        PkiFree(v1);
        return 0;
      }
    }
    else
    {
      SetLastError(0x8007000E);
    }
    return (struct _CUCS_TOKEN_ID *)v1;
  }
  return 0;
}

```

## disassembly

```asm
0x180006760  push    rbx
0x180006762  push    rbp
0x180006763  push    rdi
0x180006764  sub     rsp, 30h
0x180006768  xor     ebp, ebp
0x18000676a  lea     rax, [rsp+48h+TokenInformationLength]
0x18000676f  xor     r9d, r9d; TokenInformationLength
0x180006772  mov     [rsp+48h+TokenInformationLength], ebp
0x180006776  xor     r8d, r8d; TokenInformation
0x180006779  mov     [rsp+48h+arg_8], ebp
0x18000677d  mov     edx, 1; TokenInformationClass
0x180006782  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180006787  mov     ebx, ebp
0x180006789  mov     rdi, rcx
0x18000678c  call    cs:__imp_GetTokenInformation
0x180006792  mov     eax, [rsp+48h+TokenInformationLength]
0x180006796  test    eax, eax
0x180006798  jz      loc_180006895
0x18000679e  mov     [rsp+48h+arg_0], rsi
0x1800067a3  mov     rcx, rdi
0x1800067a6  lea     esi, [rax+7]
0x1800067a9  and     esi, 0FFFFFFF8h
0x1800067ac  call    I_CryptIsAppContainerToken
0x1800067b1  test    eax, eax
0x1800067b3  jnz     short loc_18000682B
0x1800067b5  mov     ecx, [rsp+48h+arg_8]
0x1800067b9  lea     edx, [rsi+10h]
0x1800067bc  add     edx, ecx; uBytes
0x1800067be  mov     ecx, 40h ; '@'; uFlags
0x1800067c3  call    cs:__imp_LocalAlloc
0x1800067c9  mov     rbx, rax
0x1800067cc  test    rax, rax
0x1800067cf  jz      loc_180006885
0x1800067d5  lea     r8, [rax+10h]; TokenInformation
0x1800067d9  mov     edx, 1; TokenInformationClass
0x1800067de  mov     [rax], r8
0x1800067e1  mov     rcx, rdi; TokenHandle
0x1800067e4  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x1800067e9  lea     rax, [rsp+48h+TokenInformationLength]
0x1800067ee  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800067f3  call    cs:__imp_GetTokenInformation
0x1800067f9  test    eax, eax
0x1800067fb  jz      short loc_180006813
0x1800067fd  cmp     [rsp+48h+arg_8], ebp
0x180006801  jnz     short loc_180006857
0x180006803  mov     rsi, [rsp+48h+arg_0]
0x180006808  mov     rax, rbx
0x18000680b  add     rsp, 30h
0x18000680f  pop     rdi
0x180006810  pop     rbp
0x180006811  pop     rbx
0x180006812  retn
0x180006813  mov     rcx, rbx; hMem
0x180006816  call    PkiFree
0x18000681b  mov     rsi, [rsp+48h+arg_0]
0x180006820  mov     rax, rbp
0x180006823  add     rsp, 30h
0x180006827  pop     rdi
0x180006828  pop     rbp
0x180006829  pop     rbx
0x18000682a  retn
0x18000682b  lea     rax, [rsp+48h+arg_8]
0x180006830  xor     r9d, r9d; TokenInformationLength
0x180006833  xor     r8d, r8d; TokenInformation
0x180006836  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000683b  mov     edx, 1Fh; TokenInformationClass
0x180006840  mov     rcx, rdi; TokenHandle
0x180006843  call    cs:__imp_GetTokenInformation
0x180006849  mov     ecx, [rsp+48h+arg_8]
0x18000684d  test    ecx, ecx
0x18000684f  jnz     loc_1800067B9
0x180006855  jmp     short loc_180006803
0x180006857  lea     rax, [rsp+48h+arg_8]
0x18000685c  mov     edx, 1Fh; TokenInformationClass
0x180006861  lea     r8, [rsi+10h]
0x180006865  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000686a  add     r8, rbx; TokenInformation
0x18000686d  mov     rcx, rdi; TokenHandle
0x180006870  mov     [rbx+8], r8
0x180006874  mov     r9d, [rsp+48h+arg_8]; TokenInformationLength
0x180006879  call    cs:__imp_GetTokenInformation
0x18000687f  test    eax, eax
0x180006881  jnz     short loc_180006803
0x180006883  jmp     short loc_180006813
0x180006885  mov     ecx, 8007000Eh; dwErrCode
0x18000688a  call    cs:__imp_SetLastError
0x180006890  jmp     loc_180006803
0x180006895  mov     rax, rbx
0x180006898  jmp     loc_18000680B
```
