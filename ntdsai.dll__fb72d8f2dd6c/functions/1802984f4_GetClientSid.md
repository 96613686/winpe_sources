# GetClientSid

- ea: `0x1802984f4`
- end: `0x180298648`
- name: `GetClientSid`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1802987c4`

## callees

- `0x1800f80e0`
- `0x1800f8280`
- `0x1802984f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18029853c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18029853c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180298527`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180298527`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1802985cc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1802985cc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180298600`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180298600`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18029856d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802985a9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18029856d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802985a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180298546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180298573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802985b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180298546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180298573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802985b3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180298585`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802985d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180298585`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802985d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180298615`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180298615`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180298624`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180298624`

## pseudocode

```c
__int64 __fastcall GetClientSid(_QWORD *a1)
{
  int v1; // esi
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  PSID *v5; // rdi
  HLOCAL v6; // rax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF

  v1 = 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  LastError = ImpersonateAnyClient();
  if ( !LastError )
  {
    v1 = 1;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x2000000u, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      goto LABEL_19;
    }
    v5 = 0;
    TokenInformationLength = 0;
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      v5 = (PSID *)LocalAlloc(0, TokenInformationLength);
      if ( !v5 )
      {
        LastError = 8;
        goto LABEL_19;
      }
      if ( GetTokenInformation(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
      {
        LastError = 0;
        goto LABEL_10;
      }
      LastError = GetLastError();
    }
    if ( LastError )
      goto LABEL_17;
    if ( !v5 )
    {
LABEL_16:
      LastError = 1309;
LABEL_17:
      if ( !v5 )
        goto LABEL_19;
      goto LABEL_18;
    }
LABEL_10:
    if ( *v5 )
    {
      TokenInformationLength = GetLengthSid(*v5);
      v6 = LocalAlloc(0, TokenInformationLength);
      *a1 = v6;
      if ( v6 )
        CopySid(TokenInformationLength, v6, *v5);
      else
        LastError = 8;
LABEL_18:
      LocalFree(v5);
      goto LABEL_19;
    }
    goto LABEL_16;
  }
LABEL_19:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v1 )
    UnImpersonateAnyClient();
  return LastError;
}

```

## disassembly

```asm
0x1802984f4  mov     [rsp-18h+arg_0], rbx
0x1802984f9  mov     [rsp-18h+arg_18], rsi
0x1802984fe  push    rbp
0x1802984ff  push    rdi
0x180298500  push    r14
0x180298502  mov     rbp, rsp
0x180298505  sub     rsp, 30h
0x180298509  xor     esi, esi
0x18029850b  mov     r14, rcx
0x18029850e  mov     [rbp+TokenHandle], rsi
0x180298512  mov     [rbp+TokenInformationLength], esi
0x180298515  call    ImpersonateAnyClient
0x18029851a  mov     ebx, eax
0x18029851c  test    eax, eax
0x18029851e  jnz     loc_18029861B
0x180298524  lea     esi, [rax+1]
0x180298527  call    cs:__imp_GetCurrentThread
0x18029852d  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180298531  mov     r8d, esi; OpenAsSelf
0x180298534  mov     rcx, rax; ThreadHandle
0x180298537  mov     edx, 2000000h; DesiredAccess
0x18029853c  call    cs:__imp_OpenThreadToken
0x180298542  test    eax, eax
0x180298544  jnz     short loc_180298553
0x180298546  call    cs:__imp_GetLastError
0x18029854c  mov     ebx, eax
0x18029854e  jmp     loc_18029861B
0x180298553  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180298557  lea     rax, [rbp+TokenInformationLength]
0x18029855b  xor     edi, edi
0x18029855d  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180298562  xor     r9d, r9d; TokenInformationLength
0x180298565  mov     [rbp+TokenInformationLength], edi
0x180298568  xor     r8d, r8d; TokenInformation
0x18029856b  mov     edx, esi; TokenInformationClass
0x18029856d  call    cs:__imp_GetTokenInformation
0x180298573  call    cs:__imp_GetLastError
0x180298579  mov     ebx, eax
0x18029857b  cmp     eax, 7Ah ; 'z'
0x18029857e  jnz     short loc_1802985BB
0x180298580  mov     edx, [rbp+TokenInformationLength]; uBytes
0x180298583  xor     ecx, ecx; uFlags
0x180298585  call    cs:__imp_LocalAlloc
0x18029858b  mov     rdi, rax
0x18029858e  test    rax, rax
0x180298591  jz      short loc_1802985F0
0x180298593  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180298597  lea     rax, [rbp+TokenInformationLength]
0x18029859b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18029859f  mov     r8, rdi; TokenInformation
0x1802985a2  mov     edx, esi; TokenInformationClass
0x1802985a4  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1802985a9  call    cs:__imp_GetTokenInformation
0x1802985af  test    eax, eax
0x1802985b1  jnz     short loc_1802985EC
0x1802985b3  call    cs:__imp_GetLastError
0x1802985b9  mov     ebx, eax
0x1802985bb  test    ebx, ebx
0x1802985bd  jnz     short loc_18029860D
0x1802985bf  test    rdi, rdi
0x1802985c2  jz      short loc_180298608
0x1802985c4  mov     rcx, [rdi]; pSid
0x1802985c7  test    rcx, rcx
0x1802985ca  jz      short loc_180298608
0x1802985cc  call    cs:__imp_GetLengthSid
0x1802985d2  mov     edx, eax; uBytes
0x1802985d4  xor     ecx, ecx; uFlags
0x1802985d6  mov     [rbp+TokenInformationLength], edx
0x1802985d9  call    cs:__imp_LocalAlloc
0x1802985df  mov     [r14], rax
0x1802985e2  test    rax, rax
0x1802985e5  jnz     short loc_1802985F7
0x1802985e7  lea     ebx, [rax+8]
0x1802985ea  jmp     short loc_180298612
0x1802985ec  xor     ebx, ebx
0x1802985ee  jmp     short loc_1802985C4
0x1802985f0  mov     ebx, 8
0x1802985f5  jmp     short loc_18029861B
0x1802985f7  mov     r8, [rdi]; pSourceSid
0x1802985fa  mov     rdx, rax; pDestinationSid
0x1802985fd  mov     ecx, [rbp+TokenInformationLength]; nDestinationSidLength
0x180298600  call    cs:__imp_CopySid
0x180298606  jmp     short loc_180298612
0x180298608  mov     ebx, 51Dh
0x18029860d  test    rdi, rdi
0x180298610  jz      short loc_18029861B
0x180298612  mov     rcx, rdi; hMem
0x180298615  call    cs:__imp_LocalFree
0x18029861b  mov     rcx, [rbp+TokenHandle]; hObject
0x18029861f  test    rcx, rcx
0x180298622  jz      short loc_18029862A
0x180298624  call    cs:__imp_CloseHandle
0x18029862a  test    esi, esi
0x18029862c  jz      short loc_180298633
0x18029862e  call    UnImpersonateAnyClient
0x180298633  mov     rsi, [rsp+30h+arg_18]
0x180298638  mov     eax, ebx
0x18029863a  mov     rbx, [rsp+30h+arg_0]
0x18029863f  add     rsp, 30h
0x180298643  pop     r14
0x180298645  pop     rdi
0x180298646  pop     rbp
0x180298647  retn
```
