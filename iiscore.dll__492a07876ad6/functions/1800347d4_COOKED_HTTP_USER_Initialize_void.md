# COOKED_HTTP_USER::Initialize(void)

- ea: `0x1800347d4`
- end: `0x180034961`
- name: `?Initialize@COOKED_HTTP_USER@@SAJXZ`
- size: `397`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d408`

## callees

- `0x1800347d4`
- `0x180037790`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800347f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800347f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003480e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003480e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800348e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034905`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800348e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800348b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800348b7`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180034847`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003486f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180034847`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003486f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800348a7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800348a7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180034931`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180034931`

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
0x1800347d4  mov     [rsp+arg_0], rbx
0x1800347d9  push    rsi
0x1800347da  sub     rsp, 0B0h
0x1800347e1  mov     rax, cs:__security_cookie
0x1800347e8  xor     rax, rsp
0x1800347eb  mov     [rsp+0B8h+var_18], rax
0x1800347f3  call    cs:__imp_GetCurrentProcess
0x1800347fa  nop     dword ptr [rax+rax+00h]
0x1800347ff  lea     r8, ?sm_hProcessPrimaryToken@COOKED_HTTP_USER@@0PEAXEA; TokenHandle
0x180034806  mov     edx, 0F01FFh; DesiredAccess
0x18003480b  mov     rcx, rax; ProcessHandle
0x18003480e  call    cs:__imp_OpenProcessToken
0x180034815  nop     dword ptr [rax+rax+00h]
0x18003481a  test    eax, eax
0x18003481c  jz      loc_1800348B7
0x180034822  mov     rcx, cs:?sm_hProcessPrimaryToken@COOKED_HTTP_USER@@0PEAXEA; hExistingToken
0x180034829  lea     rsi, ?sm_hProcessImpersonationToken@COOKED_HTTP_USER@@0PEAXEA; void * COOKED_HTTP_USER::sm_hProcessImpersonationToken
0x180034830  mov     ebx, 2
0x180034835  mov     [rsp+0B8h+phNewToken], rsi; phNewToken
0x18003483a  xor     r8d, r8d; lpTokenAttributes
0x18003483d  mov     [rsp+0B8h+TokenType], ebx; TokenType
0x180034841  xor     edx, edx; dwDesiredAccess
0x180034843  lea     r9d, [rbx+1]; ImpersonationLevel
0x180034847  call    cs:__imp_DuplicateTokenEx
0x18003484e  nop     dword ptr [rax+rax+00h]
0x180034853  test    eax, eax
0x180034855  jnz     short loc_18003487F
0x180034857  mov     rcx, cs:?sm_hProcessPrimaryToken@COOKED_HTTP_USER@@0PEAXEA; hExistingToken
0x18003485e  mov     r9d, ebx; ImpersonationLevel
0x180034861  mov     [rsp+0B8h+phNewToken], rsi; phNewToken
0x180034866  xor     r8d, r8d; lpTokenAttributes
0x180034869  xor     edx, edx; dwDesiredAccess
0x18003486b  mov     [rsp+0B8h+TokenType], ebx; TokenType
0x18003486f  call    cs:__imp_DuplicateTokenEx
0x180034876  nop     dword ptr [rax+rax+00h]
0x18003487b  test    eax, eax
0x18003487d  jz      short loc_1800348B7
0x18003487f  mov     rcx, cs:?sm_hProcessImpersonationToken@COOKED_HTTP_USER@@0PEAXEA; TokenHandle
0x180034886  lea     rax, [rsp+0B8h+ReturnLength]
0x18003488b  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180034891  mov     [rsp+0B8h+ReturnLength], 0
0x180034899  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x18003489e  mov     qword ptr [rsp+0B8h+TokenType], rax; ReturnLength
0x1800348a3  lea     edx, [r9-53h]; TokenInformationClass
0x1800348a7  call    cs:__imp_GetTokenInformation
0x1800348ae  nop     dword ptr [rax+rax+00h]
0x1800348b3  test    eax, eax
0x1800348b5  jnz     short loc_180034920
0x1800348b7  call    cs:__imp_GetLastError
0x1800348be  nop     dword ptr [rax+rax+00h]
0x1800348c3  mov     ebx, eax
0x1800348c5  test    eax, eax
0x1800348c7  jle     short loc_1800348D2
0x1800348c9  movzx   ebx, ax
0x1800348cc  or      ebx, 80070000h
0x1800348d2  test    ebx, ebx
0x1800348d4  jns     short loc_18003493D
0x1800348d6  mov     rcx, cs:?sm_hProcessPrimaryToken@COOKED_HTTP_USER@@0PEAXEA; hObject
0x1800348dd  test    rcx, rcx
0x1800348e0  jz      short loc_1800348F9
0x1800348e2  call    cs:__imp_CloseHandle
0x1800348e9  nop     dword ptr [rax+rax+00h]
0x1800348ee  mov     cs:?sm_hProcessPrimaryToken@COOKED_HTTP_USER@@0PEAXEA, 0; void * COOKED_HTTP_USER::sm_hProcessPrimaryToken
0x1800348f9  mov     rcx, cs:?sm_hProcessImpersonationToken@COOKED_HTTP_USER@@0PEAXEA; hObject
0x180034900  test    rcx, rcx
0x180034903  jz      short loc_18003491C
0x180034905  call    cs:__imp_CloseHandle
0x18003490c  nop     dword ptr [rax+rax+00h]
0x180034911  mov     cs:?sm_hProcessImpersonationToken@COOKED_HTTP_USER@@0PEAXEA, 0; void * COOKED_HTTP_USER::sm_hProcessImpersonationToken
0x18003491c  xor     ebx, ebx
0x18003491e  jmp     short loc_18003493D
0x180034920  mov     r8, [rsp+0B8h+TokenInformation]; pSourceSid
0x180034925  lea     rdx, ?sm_abProcessUserSid@COOKED_HTTP_USER@@0PAEA; pDestinationSid
0x18003492c  xor     ebx, ebx
0x18003492e  lea     ecx, [rbx+44h]; nDestinationSidLength
0x180034931  call    cs:__imp_CopySid
0x180034938  nop     dword ptr [rax+rax+00h]
0x18003493d  mov     eax, ebx
0x18003493f  mov     rcx, [rsp+0B8h+var_18]
0x180034947  xor     rcx, rsp; StackCookie
0x18003494a  call    __security_check_cookie
0x18003494f  mov     rbx, [rsp+0B8h+arg_0]
0x180034957  add     rsp, 0B0h
0x18003495e  pop     rsi
0x18003495f  retn
```
