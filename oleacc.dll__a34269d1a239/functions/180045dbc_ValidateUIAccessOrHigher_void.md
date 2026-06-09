# ValidateUIAccessOrHigher(void)

- ea: `0x180045dbc`
- end: `0x180045e65`
- name: `?ValidateUIAccessOrHigher@@YAJXZ`
- size: `169`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180045f04`
- `0x1800465d0`

## callees

- `0x180045ad8`
- `0x180045dbc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045e52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045e52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180045dd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180045dd4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180045de7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180045de7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045e2f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045e2f`

## pseudocode

```c
__int64 ValidateUIAccessOrHigher(void)
{
  unsigned int v0; // ebx
  HANDLE CurrentProcess; // rax
  int v2; // edi
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v0 = -2147024891;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    if ( GetTokenIl(TokenHandle) >= 0x3000 )
    {
      v0 = 0;
    }
    else
    {
      v2 = 0;
      TokenInformation = 0;
      ReturnLength = 0;
      if ( GetTokenInformation(TokenHandle, TokenUIAccess, &TokenInformation, 4u, &ReturnLength) )
        LOBYTE(v2) = TokenInformation != 0;
      v0 = v2 == 0 ? 0x80070005 : 0;
    }
    CloseHandle(TokenHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x180045dbc  mov     [rsp+arg_18], rbx
0x180045dc1  push    rdi
0x180045dc2  sub     rsp, 30h
0x180045dc6  mov     ebx, 80070005h
0x180045dcb  mov     [rsp+38h+TokenHandle], 0
0x180045dd4  call    cs:__imp_GetCurrentProcess
0x180045dda  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180045ddf  mov     edx, 8; DesiredAccess
0x180045de4  mov     rcx, rax; ProcessHandle
0x180045de7  call    cs:__imp_OpenProcessToken
0x180045ded  test    eax, eax
0x180045def  jz      short loc_180045E58
0x180045df1  mov     rcx, [rsp+38h+TokenHandle]; void *
0x180045df6  call    ?GetTokenIl@@YAKPEAX@Z; GetTokenIl(void *)
0x180045dfb  cmp     eax, 3000h
0x180045e00  jnb     short loc_180045E4B
0x180045e02  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180045e07  lea     rax, [rsp+38h+arg_8]
0x180045e0c  xor     edi, edi
0x180045e0e  mov     [rsp+38h+TokenInformation], 0
0x180045e16  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180045e1b  mov     [rsp+38h+arg_8], 0
0x180045e23  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180045e28  lea     r9d, [rdi+4]; TokenInformationLength
0x180045e2c  lea     edx, [rdi+1Ah]; TokenInformationClass
0x180045e2f  call    cs:__imp_GetTokenInformation
0x180045e35  test    eax, eax
0x180045e37  jz      short loc_180045E41
0x180045e39  cmp     [rsp+38h+TokenInformation], edi
0x180045e3d  setnz   dil
0x180045e41  neg     edi
0x180045e43  sbb     eax, eax
0x180045e45  not     eax
0x180045e47  and     ebx, eax
0x180045e49  jmp     short loc_180045E4D
0x180045e4b  xor     ebx, ebx
0x180045e4d  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180045e52  call    cs:__imp_CloseHandle
0x180045e58  mov     eax, ebx
0x180045e5a  mov     rbx, [rsp+38h+arg_18]
0x180045e5f  add     rsp, 30h
0x180045e63  pop     rdi
0x180045e64  retn
```
