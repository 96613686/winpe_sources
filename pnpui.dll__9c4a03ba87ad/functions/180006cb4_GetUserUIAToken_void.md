# GetUserUIAToken(void *)

- ea: `0x180006cb4`
- end: `0x180006d65`
- name: `?GetUserUIAToken@@YAPEAXPEAX@Z`
- size: `177`
- prototype: `void *__fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007080`

## callees

- `0x180006cb4`
- `0x18000a9cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006d51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006d51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cf7`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180006ced`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180006ced`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180006d2e`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180006d2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d49`

## pseudocode

```c
HANDLE __fastcall GetUserUIAToken(char *a1)
{
  HANDLE v1; // rdi
  DWORD LastError; // ebx
  HANDLE v3; // rcx
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  if ( (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = 87;
  }
  else if ( !DuplicateTokenEx(a1, 0, 0, SecurityImpersonation, TokenPrimary, &TokenHandle)
         || (LastError = LUASetUIAToken2(&TokenHandle)) == 0
         && (v1 = TokenHandle,
             v3 = TokenHandle,
             TokenHandle = 0,
             !SetTokenInformation(v3, TokenUIAccess, &TokenInformation, 4u)) )
  {
    LastError = GetLastError();
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  SetLastError(LastError);
  return v1;
}

```

## disassembly

```asm
0x180006cb4  mov     r11, rsp
0x180006cb7  mov     [r11+18h], rbx
0x180006cbb  push    rdi
0x180006cbc  sub     rsp, 30h
0x180006cc0  xor     edi, edi
0x180006cc2  lea     rax, [rcx-1]
0x180006cc6  mov     [r11+10h], rdi
0x180006cca  mov     [rsp+38h+TokenInformation], edi
0x180006cce  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006cd2  ja      short loc_180006D3A
0x180006cd4  lea     rax, [r11+10h]
0x180006cd8  xor     r8d, r8d; lpTokenAttributes
0x180006cdb  mov     [r11-10h], rax
0x180006cdf  lea     r9d, [rdi+2]; ImpersonationLevel
0x180006ce3  xor     edx, edx; dwDesiredAccess
0x180006ce5  mov     [rsp+38h+TokenType], 1; TokenType
0x180006ced  call    cs:__imp_DuplicateTokenEx
0x180006cf3  test    eax, eax
0x180006cf5  jnz     short loc_180006D01
0x180006cf7  call    cs:__imp_GetLastError
0x180006cfd  mov     ebx, eax
0x180006cff  jmp     short loc_180006D3F
0x180006d01  lea     rcx, [rsp+38h+TokenHandle]
0x180006d06  call    LUASetUIAToken2
0x180006d0b  mov     ebx, eax
0x180006d0d  test    eax, eax
0x180006d0f  jnz     short loc_180006D3F
0x180006d11  mov     rdi, [rsp+38h+TokenHandle]
0x180006d16  lea     r9d, [rax+4]; TokenInformationLength
0x180006d1a  mov     rcx, rdi; TokenHandle
0x180006d1d  mov     [rsp+38h+TokenHandle], 0
0x180006d26  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180006d2b  lea     edx, [rax+1Ah]; TokenInformationClass
0x180006d2e  call    cs:__imp_SetTokenInformation
0x180006d34  test    eax, eax
0x180006d36  jnz     short loc_180006D3F
0x180006d38  jmp     short loc_180006CF7
0x180006d3a  mov     ebx, 57h ; 'W'
0x180006d3f  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180006d44  test    rcx, rcx
0x180006d47  jz      short loc_180006D4F
0x180006d49  call    cs:__imp_CloseHandle
0x180006d4f  mov     ecx, ebx; dwErrCode
0x180006d51  call    cs:__imp_SetLastError
0x180006d57  mov     rbx, [rsp+38h+arg_10]
0x180006d5c  mov     rax, rdi
0x180006d5f  add     rsp, 30h
0x180006d63  pop     rdi
0x180006d64  retn
```
