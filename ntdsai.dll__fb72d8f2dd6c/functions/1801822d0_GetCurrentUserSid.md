# GetCurrentUserSid

- ea: `0x1801822d0`
- end: `0x1801823df`
- name: `GetCurrentUserSid`
- size: `271`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180181460`
- `0x1803823d4`

## callees

- `0x180021aa3`
- `0x1800f80e0`
- `0x1800f8280`
- `0x1801822d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18018238c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18018238c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18018231b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18018231b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180182305`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180182305`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180182381`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180182381`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18018233f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180182374`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18018233f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180182374`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18018234f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18018234f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801823c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801823c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801823b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801823b3`

## pseudocode

```c
void *GetCurrentUserSid()
{
  PSID *v1; // rbx
  void *v2; // rdi
  HANDLE CurrentThread; // rax
  void *v4; // rax
  DWORD TokenInformationLength; // [rsp+40h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  TokenHandle = (void *)-1LL;
  if ( ImpersonateAnyClient() )
    return 0;
  v1 = 0;
  v2 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
  {
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    {
      v1 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
      if ( v1 )
      {
        if ( GetTokenInformation(TokenHandle, TokenUser, v1, TokenInformationLength, &TokenInformationLength) )
        {
          TokenInformationLength = GetLengthSid(*v1);
          v4 = malloc(TokenInformationLength);
          v2 = v4;
          if ( v4 )
            memcpy_0(v4, *v1, TokenInformationLength);
        }
      }
    }
  }
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  UnImpersonateAnyClient();
  if ( v1 )
    LocalFree(v1);
  return v2;
}

```

## disassembly

```asm
0x1801822d0  mov     [rsp-8+arg_10], rbx
0x1801822d5  mov     [rsp-8+arg_18], rdi
0x1801822da  push    rbp
0x1801822db  mov     rbp, rsp
0x1801822de  sub     rsp, 30h
0x1801822e2  mov     [rbp+TokenInformationLength], 0
0x1801822e9  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1801822f1  call    ImpersonateAnyClient
0x1801822f6  test    eax, eax
0x1801822f8  jz      short loc_180182301
0x1801822fa  xor     eax, eax
0x1801822fc  jmp     loc_1801823CF
0x180182301  xor     ebx, ebx
0x180182303  xor     edi, edi
0x180182305  call    cs:__imp_GetCurrentThread
0x18018230b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18018230f  mov     edx, 20008h; DesiredAccess
0x180182314  mov     rcx, rax; ThreadHandle
0x180182317  lea     r8d, [rbx+1]; OpenAsSelf
0x18018231b  call    cs:__imp_OpenThreadToken
0x180182321  test    eax, eax
0x180182323  jz      loc_1801823A9
0x180182329  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18018232d  lea     rax, [rbp+TokenInformationLength]
0x180182331  xor     r9d, r9d; TokenInformationLength
0x180182334  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180182339  xor     r8d, r8d; TokenInformation
0x18018233c  lea     edx, [rbx+1]; TokenInformationClass
0x18018233f  call    cs:__imp_GetTokenInformation
0x180182345  test    eax, eax
0x180182347  jnz     short loc_1801823A9
0x180182349  mov     edx, [rbp+TokenInformationLength]; uBytes
0x18018234c  lea     ecx, [rbx+40h]; uFlags
0x18018234f  call    cs:__imp_LocalAlloc
0x180182355  mov     rbx, rax
0x180182358  test    rax, rax
0x18018235b  jz      short loc_1801823A9
0x18018235d  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180182361  lea     rax, [rbp+TokenInformationLength]
0x180182365  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180182369  lea     edx, [rdi+1]; TokenInformationClass
0x18018236c  mov     r8, rbx; TokenInformation
0x18018236f  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180182374  call    cs:__imp_GetTokenInformation
0x18018237a  test    eax, eax
0x18018237c  jz      short loc_1801823A9
0x18018237e  mov     rcx, [rbx]; pSid
0x180182381  call    cs:__imp_GetLengthSid
0x180182387  mov     ecx, eax; Size
0x180182389  mov     [rbp+TokenInformationLength], ecx
0x18018238c  call    cs:__imp_malloc
0x180182392  mov     rdi, rax
0x180182395  test    rax, rax
0x180182398  jz      short loc_1801823A9
0x18018239a  mov     r8d, [rbp+TokenInformationLength]; Size
0x18018239e  mov     rcx, rax; void *
0x1801823a1  mov     rdx, [rbx]; Src
0x1801823a4  call    memcpy_0
0x1801823a9  mov     rcx, [rbp+TokenHandle]; hObject
0x1801823ad  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801823b1  jz      short loc_1801823B9
0x1801823b3  call    cs:__imp_CloseHandle
0x1801823b9  call    UnImpersonateAnyClient
0x1801823be  test    rbx, rbx
0x1801823c1  jz      short loc_1801823CC
0x1801823c3  mov     rcx, rbx; hMem
0x1801823c6  call    cs:__imp_LocalFree
0x1801823cc  mov     rax, rdi
0x1801823cf  mov     rbx, [rsp+30h+arg_10]
0x1801823d4  mov     rdi, [rsp+30h+arg_18]
0x1801823d9  add     rsp, 30h
0x1801823dd  pop     rbp
0x1801823de  retn
```
