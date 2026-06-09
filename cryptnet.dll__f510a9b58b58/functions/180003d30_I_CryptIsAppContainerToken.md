# I_CryptIsAppContainerToken

- ea: `0x180003d30`
- end: `0x180003dd1`
- name: `I_CryptIsAppContainerToken`
- size: `161`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003170`
- `0x180003b40`

## callees

- `0x180003d30`
- `0x180006c94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003da1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003da1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d99`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003d67`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003d67`

## pseudocode

```c
__int64 __fastcall I_CryptIsAppContainerToken(void *a1)
{
  unsigned int v1; // esi
  void *v2; // rdi
  DWORD LastError; // ebx
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
0x180003d30  mov     [rsp+arg_18], rsi
0x180003d35  push    rdi
0x180003d36  sub     rsp, 30h
0x180003d3a  xor     eax, eax
0x180003d3c  mov     [rsp+38h+TokenInformation], eax
0x180003d40  mov     esi, eax
0x180003d42  mov     [rsp+38h+arg_0], eax
0x180003d46  mov     edi, eax
0x180003d48  test    rcx, rcx
0x180003d4b  jz      short loc_180003DBC
0x180003d4d  lea     rax, [rsp+38h+arg_0]
0x180003d52  mov     r9d, 4; TokenInformationLength
0x180003d58  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180003d5d  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180003d62  mov     edx, 1Dh; TokenInformationClass
0x180003d67  call    cs:__imp_GetTokenInformation
0x180003d6d  test    eax, eax
0x180003d6f  jz      short loc_180003D77
0x180003d71  cmp     [rsp+38h+TokenInformation], esi
0x180003d75  jnz     short loc_180003DAE
0x180003d77  test    rdi, rdi
0x180003d7a  jnz     short loc_180003D89
0x180003d7c  mov     eax, esi
0x180003d7e  mov     rsi, [rsp+38h+arg_18]
0x180003d83  add     rsp, 30h
0x180003d87  pop     rdi
0x180003d88  retn
0x180003d89  mov     [rsp+38h+arg_10], rbx
0x180003d8e  call    cs:__imp_GetLastError
0x180003d94  mov     rcx, rdi; hObject
0x180003d97  mov     ebx, eax
0x180003d99  call    cs:__imp_CloseHandle
0x180003d9f  mov     ecx, ebx; dwErrCode
0x180003da1  call    cs:__imp_SetLastError
0x180003da7  mov     rbx, [rsp+38h+arg_10]
0x180003dac  jmp     short loc_180003D7C
0x180003dae  cmp     [rsp+38h+arg_0], 4
0x180003db3  jnz     short loc_180003D77
0x180003db5  mov     esi, 1
0x180003dba  jmp     short loc_180003D77
0x180003dbc  call    I_CryptGetToken
0x180003dc1  mov     rdi, rax
0x180003dc4  test    rax, rax
0x180003dc7  jz      short loc_180003D7C
0x180003dc9  mov     rcx, rax
0x180003dcc  jmp     loc_180003D4D
```
