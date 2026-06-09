# GetTokenAuthenticationId

- ea: `0x1800032b4`
- end: `0x1800033a2`
- name: `GetTokenAuthenticationId`
- size: `238`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002f18`
- `0x180003b98`
- `0x180029818`

## callees

- `0x1800032b4`
- `0x18001d810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003316`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003316`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003385`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003385`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003369`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003369`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000332d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000332d`

## pseudocode

```c
__int64 __fastcall GetTokenAuthenticationId(HANDLE a1, _QWORD *a2)
{
  HANDLE v3; // rbx
  BOOL v4; // edi
  __int64 result; // rax
  HANDLE CurrentThread; // rax
  HANDLE hObject; // [rsp+30h] [rbp-50h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-48h] BYREF
  _OWORD TokenInformation[3]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v10; // [rsp+70h] [rbp-10h]

  v10 = 0;
  ReturnLength = 0;
  v3 = a1;
  hObject = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( a1 )
  {
    hObject = a1;
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &hObject) )
      return 0;
    a1 = hObject;
  }
  v4 = GetTokenInformation(a1, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
  if ( hObject != v3 )
    CloseHandle(hObject);
  if ( v4 )
  {
    result = 1;
    *a2 = *((_QWORD *)&TokenInformation[0] + 1);
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x1800032b4  mov     [rsp-18h+arg_10], rbx
0x1800032b9  push    rbp
0x1800032ba  push    rsi
0x1800032bb  push    rdi
0x1800032bc  mov     rbp, rsp
0x1800032bf  sub     rsp, 80h
0x1800032c6  mov     rax, cs:__security_cookie
0x1800032cd  xor     rax, rsp
0x1800032d0  mov     [rbp+var_8], rax
0x1800032d4  xor     eax, eax
0x1800032d6  xorps   xmm0, xmm0
0x1800032d9  mov     [rbp+var_10], rax
0x1800032dd  mov     rsi, rdx
0x1800032e0  mov     [rbp+var_48], eax
0x1800032e3  mov     rbx, rcx
0x1800032e6  mov     [rbp+hObject], rax
0x1800032ea  movups  [rbp+TokenInformation], xmm0
0x1800032ee  movups  [rbp+var_30], xmm0
0x1800032f2  movups  [rbp+var_20], xmm0
0x1800032f6  test    rcx, rcx
0x1800032f9  jz      short loc_180003369
0x1800032fb  mov     [rbp+hObject], rcx
0x1800032ff  mov     r9d, 38h ; '8'; TokenInformationLength
0x180003305  lea     rax, [rbp+var_48]
0x180003309  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18000330d  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180003312  lea     edx, [r9-2Eh]; TokenInformationClass
0x180003316  call    cs:__imp_GetTokenInformation
0x18000331d  nop     dword ptr [rax+rax+00h]
0x180003322  mov     rcx, [rbp+hObject]; hObject
0x180003326  mov     edi, eax
0x180003328  cmp     rcx, rbx
0x18000332b  jz      short loc_180003339
0x18000332d  call    cs:__imp_CloseHandle
0x180003334  nop     dword ptr [rax+rax+00h]
0x180003339  test    edi, edi
0x18000333b  jz      short loc_18000339E
0x18000333d  mov     rcx, qword ptr [rbp+TokenInformation+8]
0x180003341  mov     eax, 1
0x180003346  mov     [rsi], rcx
0x180003349  mov     rcx, [rbp+var_8]
0x18000334d  xor     rcx, rsp; StackCookie
0x180003350  call    __security_check_cookie
0x180003355  mov     rbx, [rsp+80h+arg_10]
0x18000335d  add     rsp, 80h
0x180003364  pop     rdi
0x180003365  pop     rsi
0x180003366  pop     rbp
0x180003367  retn
0x180003369  call    cs:__imp_GetCurrentThread
0x180003370  nop     dword ptr [rax+rax+00h]
0x180003375  mov     edx, 8; DesiredAccess
0x18000337a  lea     r9, [rbp+hObject]; TokenHandle
0x18000337e  mov     rcx, rax; ThreadHandle
0x180003381  lea     r8d, [rdx-7]; OpenAsSelf
0x180003385  call    cs:__imp_OpenThreadToken
0x18000338c  nop     dword ptr [rax+rax+00h]
0x180003391  test    eax, eax
0x180003393  jz      short loc_18000339E
0x180003395  mov     rcx, [rbp+hObject]
0x180003399  jmp     loc_1800032FF
0x18000339e  xor     eax, eax
0x1800033a0  jmp     short loc_180003349
```
