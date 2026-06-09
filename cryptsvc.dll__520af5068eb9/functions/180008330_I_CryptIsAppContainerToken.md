# I_CryptIsAppContainerToken

- ea: `0x180008330`
- end: `0x1800083ca`
- name: `I_CryptIsAppContainerToken`
- size: `154`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006760`
- `0x180006db0`
- `0x180009030`
- `0x180009530`
- `0x18000fcd8`

## callees

- `0x180008330`
- `0x1800092e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000838d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000838d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800083a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800083a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008398`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008398`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008367`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008367`

## pseudocode

```c
__int64 __fastcall I_CryptIsAppContainerToken(void *a1)
{
  unsigned int v1; // esi
  void *v2; // rbx
  DWORD LastError; // edi
  void *Token; // rax
  DWORD ReturnLength; // [rsp+40h] [rbp+8h] BYREF
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF

  TokenInformation = 0;
  v1 = 0;
  ReturnLength = 0;
  v2 = 0;
  if ( !a1 )
  {
    Token = I_CryptGetToken();
    v2 = Token;
    if ( !Token )
      return v1;
    a1 = Token;
  }
  if ( GetTokenInformation(a1, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength)
    && TokenInformation
    && ReturnLength == 4 )
  {
    v1 = 1;
  }
  if ( v2 )
  {
    LastError = GetLastError();
    CloseHandle(v2);
    SetLastError(LastError);
  }
  return v1;
}

```

## disassembly

```asm
0x180008330  mov     [rsp+arg_18], rbx
0x180008335  push    rsi
0x180008336  sub     rsp, 30h
0x18000833a  xor     eax, eax
0x18000833c  mov     [rsp+38h+TokenInformation], eax
0x180008340  mov     esi, eax
0x180008342  mov     [rsp+38h+arg_0], eax
0x180008346  mov     ebx, eax
0x180008348  test    rcx, rcx
0x18000834b  jz      short loc_1800083B8
0x18000834d  lea     rax, [rsp+38h+arg_0]
0x180008352  mov     r9d, 4; TokenInformationLength
0x180008358  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18000835d  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180008362  mov     edx, 1Dh; TokenInformationClass
0x180008367  call    cs:__imp_GetTokenInformation
0x18000836d  test    eax, eax
0x18000836f  jz      short loc_180008383
0x180008371  cmp     [rsp+38h+TokenInformation], esi
0x180008375  jz      short loc_180008383
0x180008377  cmp     [rsp+38h+arg_0], 4
0x18000837c  jnz     short loc_180008383
0x18000837e  mov     esi, 1
0x180008383  test    rbx, rbx
0x180008386  jz      short loc_1800083AB
0x180008388  mov     [rsp+38h+arg_10], rdi
0x18000838d  call    cs:__imp_GetLastError
0x180008393  mov     rcx, rbx; hObject
0x180008396  mov     edi, eax
0x180008398  call    cs:__imp_CloseHandle
0x18000839e  mov     ecx, edi; dwErrCode
0x1800083a0  call    cs:__imp_SetLastError
0x1800083a6  mov     rdi, [rsp+38h+arg_10]
0x1800083ab  mov     rbx, [rsp+38h+arg_18]
0x1800083b0  mov     eax, esi
0x1800083b2  add     rsp, 30h
0x1800083b6  pop     rsi
0x1800083b7  retn
0x1800083b8  call    I_CryptGetToken
0x1800083bd  mov     rbx, rax
0x1800083c0  test    rax, rax
0x1800083c3  jz      short loc_1800083AB
0x1800083c5  mov     rcx, rax
0x1800083c8  jmp     short loc_18000834D
```
