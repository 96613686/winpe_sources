# CallingApp::CallerIsAppContainer(bool &)

- ea: `0x180063ef8`
- end: `0x180064063`
- name: `?CallerIsAppContainer@CallingApp@@YAJAEA_N@Z`
- size: `363`
- prototype: `HRESULT __fastcall(bool *IsCallerAppContainer)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180061b40`

## callees

- `0x180002790`
- `0x180012988`
- `0x180063ef8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063f74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063f9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063fdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063f74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063f9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063fdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180063f83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180063f83`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180063f94`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180063f94`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180063f6a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180063f6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180063f52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180063f52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063fe9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063fe9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180063fc6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180063fc6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18006400b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18006400b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180063f1a`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180063f1a`

## pseudocode

```c
__int64 __fastcall CallingApp::CallerIsAppContainer(bool *IsCallerAppContainer)
{
  HRESULT v2; // esi
  unsigned int v3; // edi
  bool v4; // bp
  HANDLE CurrentThread; // rax
  signed int LastError; // ebx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-58h] BYREF
  int TokenInformation; // [rsp+38h] [rbp-50h] BYREF
  unsigned int ReturnLength; // [rsp+3Ch] [rbp-4Ch] BYREF

  *IsCallerAppContainer = 0;
  v2 = CoImpersonateClient();
  if ( v2 == -2147417833 )
  {
    v3 = 0;
  }
  else
  {
    v3 = v2;
    if ( v2 )
      goto LABEL_21;
  }
  TokenInformation = 0;
  v4 = 0;
  TokenHandle = 0;
  ReturnLength = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_27;
  LastError = GetLastError();
  if ( LastError != 1008 )
    goto LABEL_14;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
LABEL_27:
    if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
    {
      if ( TokenInformation )
        v4 = 1;
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
    }
    CloseHandle(TokenHandle);
    goto LABEL_14;
  }
  LastError = GetLastError();
LABEL_14:
  if ( LastError )
  {
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    else
      v3 = LastError;
  }
  else
  {
    *IsCallerAppContainer = v4;
  }
  if ( !v2 )
    CoRevertToSelf();
LABEL_21:
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_dd(
      WPP_GLOBAL_Control->Control.Logger,
      0xCu,
      WPP_23c62c4a87f335c33f4b82b787c27e30_Traceguids,
      *IsCallerAppContainer,
      v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180063ef8  push    rbx
0x180063efa  push    rbp
0x180063efb  push    rsi
0x180063efc  push    rdi
0x180063efd  push    r13
0x180063eff  push    r14
0x180063f01  sub     rsp, 58h
0x180063f05  mov     rax, cs:__security_cookie
0x180063f0c  xor     rax, rsp
0x180063f0f  mov     [rsp+88h+var_48], rax
0x180063f14  mov     r14, IsCallerAppContainer
0x180063f17  mov     byte ptr [IsCallerAppContainer], 0
0x180063f1a  call    cs:__imp_CoImpersonateClient
0x180063f20  mov     esi, eax
0x180063f22  cmp     eax, 80010117h
0x180063f27  jnz     short loc_180063F2D
0x180063f29  xor     edi, edi
0x180063f2b  jmp     short loc_180063F37
0x180063f2d  mov     edi, esi
0x180063f2f  test    esi, esi
0x180063f31  jnz     loc_180064011
0x180063f37  mov     [rsp+88h+TokenInformation], 0
0x180063f3f  xor     ebp, ebp
0x180063f41  mov     [rsp+88h+TokenHandle], 0
0x180063f4a  mov     [rsp+88h+var_4C], 0
0x180063f52  call    cs:__imp_GetCurrentThread
0x180063f58  lea     r13d, [rbp+1]
0x180063f5c  mov     IsCallerAppContainer, rax; ThreadHandle
0x180063f5f  mov     r8d, r13d; OpenAsSelf
0x180063f62  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x180063f67  lea     edx, [rbp+8]; DesiredAccess
0x180063f6a  call    cs:__imp_OpenThreadToken
0x180063f70  test    eax, eax
0x180063f72  jnz     short loc_180063FA8
0x180063f74  call    cs:__imp_GetLastError
0x180063f7a  mov     ebx, eax
0x180063f7c  cmp     eax, 3F0h
0x180063f81  jnz     short loc_180063FEF
0x180063f83  call    cs:__imp_GetCurrentProcess
0x180063f89  mov     IsCallerAppContainer, rax; ProcessHandle
0x180063f8c  lea     r8, [rsp+88h+TokenHandle]; TokenHandle
0x180063f91  lea     edx, [rbp+8]; DesiredAccess
0x180063f94  call    cs:__imp_OpenProcessToken
0x180063f9a  test    eax, eax
0x180063f9c  jnz     short loc_180063FA8
0x180063f9e  call    cs:__imp_GetLastError
0x180063fa4  mov     ebx, eax
0x180063fa6  jmp     short loc_180063FEF
0x180063fa8  mov     IsCallerAppContainer, [rsp+88h+TokenHandle]; TokenHandle
0x180063fad  lea     rax, [rsp+88h+var_4C]
0x180063fb2  mov     r9d, 4; TokenInformationLength
0x180063fb8  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x180063fbd  lea     r8, [rsp+88h+TokenInformation]; TokenInformation
0x180063fc2  lea     edx, [r9+19h]; TokenInformationClass
0x180063fc6  call    cs:__imp_GetTokenInformation
0x180063fcc  test    eax, eax
0x180063fce  jz      short loc_180063FDC
0x180063fd0  cmp     [rsp+88h+TokenInformation], ebp
0x180063fd4  cmovnz  ebp, r13d
0x180063fd8  xor     ebx, ebx
0x180063fda  jmp     short loc_180063FE4
0x180063fdc  call    cs:__imp_GetLastError
0x180063fe2  mov     ebx, eax
0x180063fe4  mov     IsCallerAppContainer, [rsp+88h+TokenHandle]; hObject
0x180063fe9  call    cs:__imp_CloseHandle
0x180063fef  test    ebx, ebx
0x180063ff1  jnz     short loc_180063FF8
0x180063ff3  mov     [r14], bpl
0x180063ff6  jmp     short loc_180064007
0x180063ff8  jg      short loc_180063FFE
0x180063ffa  mov     edi, ebx
0x180063ffc  jmp     short loc_180064007
0x180063ffe  movzx   edi, bx
0x180064001  or      edi, 80070000h
0x180064007  test    esi, esi
0x180064009  jnz     short loc_180064011
0x18006400b  call    cs:__imp_CoRevertToSelf
0x180064011  mov     IsCallerAppContainer, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180064018  lea     rax, WPP_GLOBAL_Control
0x18006401f  cmp     IsCallerAppContainer, rax
0x180064022  jz      short loc_180064047
0x180064024  test    byte ptr [IsCallerAppContainer+1Ch], 10h
0x180064028  jz      short loc_180064047
0x18006402a  movzx   r9d, byte ptr [r14]; _a1
0x18006402e  lea     r8, WPP_23c62c4a87f335c33f4b82b787c27e30_Traceguids; TraceGuid
0x180064035  mov     IsCallerAppContainer, [IsCallerAppContainer+10h]; Logger
0x180064039  mov     edx, 0Ch; id
0x18006403e  mov     dword ptr [rsp+88h+ReturnLength], edi; _a2
0x180064042  call    WPP_SF_dd
0x180064047  mov     eax, edi
0x180064049  mov     IsCallerAppContainer, [rsp+88h+var_48]
0x18006404e  xor     IsCallerAppContainer, rsp; StackCookie
0x180064051  call    __security_check_cookie
0x180064056  add     rsp, 58h
0x18006405a  pop     r14
0x18006405c  pop     r13
0x18006405e  pop     rdi
0x18006405f  pop     rsi
0x180064060  pop     rbp
0x180064061  pop     rbx
0x180064062  retn
```
