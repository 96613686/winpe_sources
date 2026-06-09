# GetThreadAuthenticationId

- ea: `0x180004d80`
- end: `0x180004e59`
- name: `GetThreadAuthenticationId`
- size: `217`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005880`
- `0x180008c3c`
- `0x18000e9c0`
- `0x180018a20`
- `0x1800193c0`
- `0x18002677c`
- `0x180029adc`
- `0x18002e310`

## callees

- `0x180004d80`
- `0x18001d810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004e06`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004e06`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004dcf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004dcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e19`

## pseudocode

```c
__int64 __fastcall GetThreadAuthenticationId(void *a1, _QWORD *a2)
{
  BOOL v3; // edi
  __int64 result; // rax
  DWORD ReturnLength; // [rsp+30h] [rbp-58h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-50h] BYREF
  _OWORD TokenInformation[3]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v8; // [rsp+70h] [rbp-18h]

  v8 = 0;
  TokenHandle = 0;
  ReturnLength = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( !OpenThreadToken(a1, 8u, 1, &TokenHandle) )
    return 0;
  v3 = GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
  CloseHandle(TokenHandle);
  if ( !v3 )
    return 0;
  result = 1;
  *a2 = *((_QWORD *)&TokenInformation[0] + 1);
  return result;
}

```

## disassembly

```asm
0x180004d80  push    rbx
0x180004d82  sub     rsp, 80h
0x180004d89  mov     rax, cs:__security_cookie
0x180004d90  xor     rax, rsp
0x180004d93  mov     [rsp+88h+var_10], rax
0x180004d98  xorps   xmm0, xmm0
0x180004d9b  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x180004da0  mov     rbx, rdx
0x180004da3  xor     eax, eax
0x180004da5  xor     edx, edx
0x180004da7  mov     [rsp+88h+var_18], rax
0x180004dac  mov     [rsp+88h+TokenHandle], rdx
0x180004db1  mov     r8d, 1; OpenAsSelf
0x180004db7  mov     [rsp+88h+var_58], edx
0x180004dbb  mov     edx, 8; DesiredAccess
0x180004dc0  movups  [rsp+88h+TokenInformation], xmm0
0x180004dc5  movups  [rsp+88h+var_38], xmm0
0x180004dca  movups  [rsp+88h+var_28], xmm0
0x180004dcf  call    cs:__imp_OpenThreadToken
0x180004dd6  nop     dword ptr [rax+rax+00h]
0x180004ddb  test    eax, eax
0x180004ddd  jz      short loc_180004E55
0x180004ddf  lea     rcx, [rsp+88h+var_58]
0x180004de4  mov     [rsp+88h+arg_10], rdi
0x180004dec  mov     [rsp+88h+ReturnLength], rcx; ReturnLength
0x180004df1  lea     r8, [rsp+88h+TokenInformation]; TokenInformation
0x180004df6  mov     rcx, [rsp+88h+TokenHandle]; TokenHandle
0x180004dfb  mov     r9d, 38h ; '8'; TokenInformationLength
0x180004e01  mov     edx, 0Ah; TokenInformationClass
0x180004e06  call    cs:__imp_GetTokenInformation
0x180004e0d  nop     dword ptr [rax+rax+00h]
0x180004e12  mov     rcx, [rsp+88h+TokenHandle]; hObject
0x180004e17  mov     edi, eax
0x180004e19  call    cs:__imp_CloseHandle
0x180004e20  nop     dword ptr [rax+rax+00h]
0x180004e25  test    edi, edi
0x180004e27  mov     rdi, [rsp+88h+arg_10]
0x180004e2f  jz      short loc_180004E55
0x180004e31  mov     rcx, qword ptr [rsp+88h+TokenInformation+8]
0x180004e36  mov     eax, 1
0x180004e3b  mov     [rbx], rcx
0x180004e3e  mov     rcx, [rsp+88h+var_10]
0x180004e43  xor     rcx, rsp; StackCookie
0x180004e46  call    __security_check_cookie
0x180004e4b  add     rsp, 80h
0x180004e52  pop     rbx
0x180004e53  retn
0x180004e55  xor     eax, eax
0x180004e57  jmp     short loc_180004E3E
```
