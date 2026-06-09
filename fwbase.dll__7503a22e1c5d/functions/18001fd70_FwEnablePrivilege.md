# FwEnablePrivilege

- ea: `0x18001fd70`
- end: `0x18001fefb`
- name: `FwEnablePrivilege`
- size: `395`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000ccd4`
- `0x18001e1d0`
- `0x18001fd70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fdd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fdd8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001fe38`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001fe38`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001fe63`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001fe63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001fdb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001fdb1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001fe75`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001fe75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001fde9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001fde9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001fdfb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001fdfb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001fdc5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001fdc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fe81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fe9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fe81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fe9e`

## pseudocode

```c
__int64 __fastcall FwEnablePrivilege(int a1)
{
  HANDLE CurrentThread; // rax
  void *v2; // rcx
  __int64 v3; // rbx
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  BOOL v6; // edi
  void *TokenHandle; // [rsp+30h] [rbp-38h] BYREF
  HANDLE Token; // [rsp+38h] [rbp-30h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-28h] BYREF

  TokenHandle = (void *)-1LL;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = 2;
  NewState.Privileges[0].Luid = (LUID)a1;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 6u, 0, &TokenHandle) )
  {
    v2 = TokenHandle;
    v3 = (__int64)TokenHandle;
    goto LABEL_6;
  }
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    v6 = OpenProcessToken(CurrentProcess, 2u, &TokenHandle);
    v3 = -1;
    if ( !v6 )
      goto LABEL_12;
    v2 = TokenHandle;
LABEL_6:
    Token = 0;
    v6 = DuplicateTokenEx(v2, 0x2Cu, 0, SecurityImpersonation, TokenImpersonation, &Token);
    if ( v6 )
    {
      v6 = AdjustTokenPrivileges(Token, 0, &NewState, 0, 0, 0);
      if ( v6 )
        v6 = SetThreadToken(0, Token);
      CloseHandle(Token);
      if ( v6 )
      {
        if ( v3 != -1 )
          return v3;
LABEL_13:
        if ( TokenHandle != (void *)-1LL )
          CloseHandle(TokenHandle);
        if ( v6 )
          return 0;
        return v3;
      }
    }
LABEL_12:
    v3 = -1;
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids, LastError);
  return -1;
}

```

## disassembly

```asm
0x18001fd70  push    rbp
0x18001fd72  push    rbx
0x18001fd73  push    rdi
0x18001fd74  push    r14
0x18001fd76  mov     rbp, rsp
0x18001fd79  sub     rsp, 68h
0x18001fd7d  mov     rax, cs:__security_cookie
0x18001fd84  xor     rax, rsp
0x18001fd87  mov     [rbp+var_18], rax
0x18001fd8b  movsxd  rax, ecx
0x18001fd8e  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001fd92  mov     rcx, rax
0x18001fd95  mov     [rbp+TokenHandle], r14
0x18001fd99  shr     rcx, 20h
0x18001fd9d  mov     [rbp+NewState.Privileges.Luid.HighPart], ecx
0x18001fda0  mov     [rbp+NewState.PrivilegeCount], 1
0x18001fda7  mov     [rbp+NewState.Privileges.Attributes], 2
0x18001fdae  mov     [rbp+NewState.Privileges.Luid.LowPart], eax
0x18001fdb1  call    cs:__imp_GetCurrentThread
0x18001fdb7  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001fdbb  xor     r8d, r8d; OpenAsSelf
0x18001fdbe  mov     rcx, rax; ThreadHandle
0x18001fdc1  lea     edx, [r14+7]; DesiredAccess
0x18001fdc5  call    cs:__imp_OpenThreadToken
0x18001fdcb  test    eax, eax
0x18001fdcd  jz      short loc_18001FDD8
0x18001fdcf  mov     rcx, [rbp+TokenHandle]
0x18001fdd3  mov     rbx, rcx
0x18001fdd6  jmp     short loc_18001FE12
0x18001fdd8  call    cs:__imp_GetLastError
0x18001fdde  cmp     eax, 3F0h
0x18001fde3  jnz     loc_18001FEB1
0x18001fde9  call    cs:__imp_GetCurrentProcess
0x18001fdef  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001fdf3  mov     edx, 2; DesiredAccess
0x18001fdf8  mov     rcx, rax; ProcessHandle
0x18001fdfb  call    cs:__imp_OpenProcessToken
0x18001fe01  mov     edi, eax
0x18001fe03  mov     rbx, r14
0x18001fe06  test    eax, eax
0x18001fe08  jz      loc_18001FE92
0x18001fe0e  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x18001fe12  mov     r9d, 2; ImpersonationLevel
0x18001fe18  mov     [rbp+Token], 0
0x18001fe20  lea     rax, [rbp+Token]
0x18001fe24  xor     r8d, r8d; lpTokenAttributes
0x18001fe27  mov     [rsp+68h+phNewToken], rax; phNewToken
0x18001fe2c  mov     [rsp+68h+TokenType], 2; TokenType
0x18001fe34  lea     edx, [r9+2Ah]; dwDesiredAccess
0x18001fe38  call    cs:__imp_DuplicateTokenEx
0x18001fe3e  mov     edi, eax
0x18001fe40  test    eax, eax
0x18001fe42  jz      short loc_18001FE92
0x18001fe44  mov     rcx, [rbp+Token]; TokenHandle
0x18001fe48  lea     r8, [rbp+NewState]; NewState
0x18001fe4c  mov     [rsp+68h+phNewToken], 0; ReturnLength
0x18001fe55  xor     r9d, r9d; BufferLength
0x18001fe58  xor     edx, edx; DisableAllPrivileges
0x18001fe5a  mov     qword ptr [rsp+68h+TokenType], 0; PreviousState
0x18001fe63  call    cs:__imp_AdjustTokenPrivileges
0x18001fe69  mov     edi, eax
0x18001fe6b  test    eax, eax
0x18001fe6d  jz      short loc_18001FE7D
0x18001fe6f  mov     rdx, [rbp+Token]; Token
0x18001fe73  xor     ecx, ecx; Thread
0x18001fe75  call    cs:__imp_SetThreadToken
0x18001fe7b  mov     edi, eax
0x18001fe7d  mov     rcx, [rbp+Token]; hObject
0x18001fe81  call    cs:__imp_CloseHandle
0x18001fe87  test    edi, edi
0x18001fe89  jz      short loc_18001FE92
0x18001fe8b  cmp     rbx, r14
0x18001fe8e  jnz     short loc_18001FEAC
0x18001fe90  jmp     short loc_18001FE95
0x18001fe92  mov     rbx, r14
0x18001fe95  mov     rcx, [rbp+TokenHandle]; hObject
0x18001fe99  cmp     rcx, r14
0x18001fe9c  jz      short loc_18001FEA4
0x18001fe9e  call    cs:__imp_CloseHandle
0x18001fea4  xor     ecx, ecx
0x18001fea6  test    edi, edi
0x18001fea8  cmovnz  rbx, rcx
0x18001feac  mov     rax, rbx
0x18001feaf  jmp     short loc_18001FEE5
0x18001feb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001feb8  lea     rdx, WPP_GLOBAL_Control
0x18001febf  cmp     rcx, rdx
0x18001fec2  jz      short loc_18001FEE2
0x18001fec4  test    byte ptr [rcx+1Ch], 1
0x18001fec8  jz      short loc_18001FEE2
0x18001feca  mov     rcx, [rcx+10h]
0x18001fece  lea     r8, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids
0x18001fed5  mov     edx, 1Dh
0x18001feda  mov     r9d, eax
0x18001fedd  call    WPP_SF_d
0x18001fee2  mov     rax, r14
0x18001fee5  mov     rcx, [rbp+var_18]
0x18001fee9  xor     rcx, rsp; StackCookie
0x18001feec  call    __security_check_cookie
0x18001fef1  add     rsp, 68h
0x18001fef5  pop     r14
0x18001fef7  pop     rdi
0x18001fef8  pop     rbx
0x18001fef9  pop     rbp
0x18001fefa  retn
```
