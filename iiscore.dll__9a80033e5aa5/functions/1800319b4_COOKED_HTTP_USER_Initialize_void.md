# COOKED_HTTP_USER::Initialize(void)

- ea: `0x1800319b4`
- end: `0x180031b0a`
- name: `?Initialize@COOKED_HTTP_USER@@SAJXZ`
- size: `342`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001bb94`

## callees

- `0x1800319b4`
- `0x1800343f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800319d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800319d3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800319e8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800319e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031a9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031abb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031a9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031abb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a79`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180031a1b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180031a3d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180031a1b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180031a3d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031a6f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031a6f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180031ae1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180031ae1`

## pseudocode

```c
__int64 COOKED_HTTP_USER::Initialize(void)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v2; // ebx
  DWORD ReturnLength[4]; // [rsp+30h] [rbp-88h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xF01FFu, &COOKED_HTTP_USER::sm_hProcessPrimaryToken)
    && (DuplicateTokenEx(
          COOKED_HTTP_USER::sm_hProcessPrimaryToken,
          0,
          0,
          SecurityDelegation,
          TokenImpersonation,
          &COOKED_HTTP_USER::sm_hProcessImpersonationToken)
     || DuplicateTokenEx(
          COOKED_HTTP_USER::sm_hProcessPrimaryToken,
          0,
          0,
          SecurityImpersonation,
          TokenImpersonation,
          &COOKED_HTTP_USER::sm_hProcessImpersonationToken))
    && (ReturnLength[0] = 0,
        GetTokenInformation(
          COOKED_HTTP_USER::sm_hProcessImpersonationToken,
          TokenUser,
          TokenInformation,
          0x54u,
          ReturnLength)) )
  {
    v2 = 0;
    CopySid(0x44u, &COOKED_HTTP_USER::sm_abProcessUserSid, TokenInformation[0]);
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 < 0 )
    {
      if ( COOKED_HTTP_USER::sm_hProcessPrimaryToken )
      {
        CloseHandle(COOKED_HTTP_USER::sm_hProcessPrimaryToken);
        COOKED_HTTP_USER::sm_hProcessPrimaryToken = 0;
      }
      if ( COOKED_HTTP_USER::sm_hProcessImpersonationToken )
      {
        CloseHandle(COOKED_HTTP_USER::sm_hProcessImpersonationToken);
        COOKED_HTTP_USER::sm_hProcessImpersonationToken = 0;
      }
      return 0;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800319b4  mov     [rsp+arg_0], rbx
0x1800319b9  push    rsi
0x1800319ba  sub     rsp, 0B0h
0x1800319c1  mov     rax, cs:__security_cookie
0x1800319c8  xor     rax, rsp
0x1800319cb  mov     [rsp+0B8h+var_18], rax
0x1800319d3  call    cs:__imp_GetCurrentProcess
0x1800319d9  lea     r8, ?sm_hProcessPrimaryToken@COOKED_HTTP_USER@@0PEAXEA; TokenHandle
0x1800319e0  mov     edx, 0F01FFh; DesiredAccess
0x1800319e5  mov     rcx, rax; ProcessHandle
0x1800319e8  call    cs:__imp_OpenProcessToken
0x1800319ee  test    eax, eax
0x1800319f0  jz      loc_180031A79
0x1800319f6  mov     rcx, cs:?sm_hProcessPrimaryToken@COOKED_HTTP_USER@@0PEAXEA; hExistingToken
0x1800319fd  lea     rsi, ?sm_hProcessImpersonationToken@COOKED_HTTP_USER@@0PEAXEA; void * COOKED_HTTP_USER::sm_hProcessImpersonationToken
0x180031a04  mov     ebx, 2
0x180031a09  mov     [rsp+0B8h+phNewToken], rsi; phNewToken
0x180031a0e  xor     r8d, r8d; lpTokenAttributes
0x180031a11  mov     [rsp+0B8h+TokenType], ebx; TokenType
0x180031a15  xor     edx, edx; dwDesiredAccess
0x180031a17  lea     r9d, [rbx+1]; ImpersonationLevel
0x180031a1b  call    cs:__imp_DuplicateTokenEx
0x180031a21  test    eax, eax
0x180031a23  jnz     short loc_180031A47
0x180031a25  mov     rcx, cs:?sm_hProcessPrimaryToken@COOKED_HTTP_USER@@0PEAXEA; hExistingToken
0x180031a2c  mov     r9d, ebx; ImpersonationLevel
0x180031a2f  mov     [rsp+0B8h+phNewToken], rsi; phNewToken
0x180031a34  xor     r8d, r8d; lpTokenAttributes
0x180031a37  xor     edx, edx; dwDesiredAccess
0x180031a39  mov     [rsp+0B8h+TokenType], ebx; TokenType
0x180031a3d  call    cs:__imp_DuplicateTokenEx
0x180031a43  test    eax, eax
0x180031a45  jz      short loc_180031A79
0x180031a47  mov     rcx, cs:?sm_hProcessImpersonationToken@COOKED_HTTP_USER@@0PEAXEA; TokenHandle
0x180031a4e  lea     rax, [rsp+0B8h+ReturnLength]
0x180031a53  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180031a59  mov     [rsp+0B8h+ReturnLength], 0
0x180031a61  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180031a66  mov     qword ptr [rsp+0B8h+TokenType], rax; ReturnLength
0x180031a6b  lea     edx, [r9-53h]; TokenInformationClass
0x180031a6f  call    cs:__imp_GetTokenInformation
0x180031a75  test    eax, eax
0x180031a77  jnz     short loc_180031AD0
0x180031a79  call    cs:__imp_GetLastError
0x180031a7f  mov     ebx, eax
0x180031a81  test    eax, eax
0x180031a83  jle     short loc_180031A8E
0x180031a85  movzx   ebx, ax
0x180031a88  or      ebx, 80070000h
0x180031a8e  test    ebx, ebx
0x180031a90  jns     short loc_180031AE7
0x180031a92  mov     rcx, cs:?sm_hProcessPrimaryToken@COOKED_HTTP_USER@@0PEAXEA; hObject
0x180031a99  test    rcx, rcx
0x180031a9c  jz      short loc_180031AAF
0x180031a9e  call    cs:__imp_CloseHandle
0x180031aa4  mov     cs:?sm_hProcessPrimaryToken@COOKED_HTTP_USER@@0PEAXEA, 0; void * COOKED_HTTP_USER::sm_hProcessPrimaryToken
0x180031aaf  mov     rcx, cs:?sm_hProcessImpersonationToken@COOKED_HTTP_USER@@0PEAXEA; hObject
0x180031ab6  test    rcx, rcx
0x180031ab9  jz      short loc_180031ACC
0x180031abb  call    cs:__imp_CloseHandle
0x180031ac1  mov     cs:?sm_hProcessImpersonationToken@COOKED_HTTP_USER@@0PEAXEA, 0; void * COOKED_HTTP_USER::sm_hProcessImpersonationToken
0x180031acc  xor     ebx, ebx
0x180031ace  jmp     short loc_180031AE7
0x180031ad0  mov     r8, [rsp+0B8h+TokenInformation]; pSourceSid
0x180031ad5  lea     rdx, ?sm_abProcessUserSid@COOKED_HTTP_USER@@0PAEA; pDestinationSid
0x180031adc  xor     ebx, ebx
0x180031ade  lea     ecx, [rbx+44h]; nDestinationSidLength
0x180031ae1  call    cs:__imp_CopySid
0x180031ae7  mov     eax, ebx
0x180031ae9  mov     rcx, [rsp+0B8h+var_18]
0x180031af1  xor     rcx, rsp; StackCookie
0x180031af4  call    __security_check_cookie
0x180031af9  mov     rbx, [rsp+0B8h+arg_0]
0x180031b01  add     rsp, 0B0h
0x180031b08  pop     rsi
0x180031b09  retn
```
