# EnablePrivilege

- ea: `0x18000e3b4`
- end: `0x18000e5a9`
- name: `EnablePrivilege`
- size: `501`
- prototype: `__int64 __fastcall(LPCWSTR lpName)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013ce0`
- `0x180013fa0`
- `0x180014200`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000e3b4`
- `0x180015cf0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000e559`
- `KERNEL32!CloseHandle` at `0x18000e576`
- `KERNEL32!CloseHandle` at `0x18000e559`
- `KERNEL32!CloseHandle` at `0x18000e576`
- `KERNEL32!GetCurrentProcess` at `0x18000e4cd`
- `KERNEL32!GetCurrentProcess` at `0x18000e4cd`
- `KERNEL32!GetLastError` at `0x18000e454`
- `KERNEL32!GetLastError` at `0x18000e4bc`
- `KERNEL32!GetLastError` at `0x18000e454`
- `KERNEL32!GetLastError` at `0x18000e4bc`
- `KERNEL32!GetCurrentThread` at `0x18000e494`
- `KERNEL32!GetCurrentThread` at `0x18000e494`
- `ADVAPI32!OpenProcessToken` at `0x18000e4dd`
- `ADVAPI32!OpenProcessToken` at `0x18000e4dd`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18000e432`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18000e432`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18000e53b`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18000e53b`
- `ADVAPI32!OpenThreadToken` at `0x18000e4a7`
- `ADVAPI32!OpenThreadToken` at `0x18000e4a7`
- `ADVAPI32!SetThreadToken` at `0x18000e54d`
- `ADVAPI32!SetThreadToken` at `0x18000e54d`
- `ADVAPI32!DuplicateTokenEx` at `0x18000e510`
- `ADVAPI32!DuplicateTokenEx` at `0x18000e510`

## pseudocode

```c
__int64 __fastcall EnablePrivilege(LPCWSTR lpName)
{
  DWORD LastError; // eax
  HANDLE CurrentThread; // rax
  BOOL v5; // edi
  HANDLE v6; // rcx
  __int64 v7; // rbx
  HANDLE CurrentProcess; // rax
  HANDLE TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  HANDLE Token; // [rsp+38h] [rbp-28h] BYREF
  _LUID Luid; // [rsp+40h] [rbp-20h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-18h] BYREF

  Luid = 0;
  TokenHandle = (HANDLE)-1LL;
  NewState = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids);
  }
  if ( LookupPrivilegeValueW(0, lpName, &Luid) )
  {
    NewState.Privileges[0].Luid = Luid;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = 2;
    CurrentThread = GetCurrentThread();
    v5 = OpenThreadToken(CurrentThread, 2u, 0, &TokenHandle);
    if ( v5 )
    {
      v6 = TokenHandle;
      v7 = (__int64)TokenHandle;
    }
    else
    {
      if ( GetLastError() != 1008 )
        goto LABEL_22;
      CurrentProcess = GetCurrentProcess();
      v5 = OpenProcessToken(CurrentProcess, 2u, &TokenHandle);
      v7 = -1;
      if ( !v5 )
        goto LABEL_22;
      v6 = TokenHandle;
    }
    Token = 0;
    v5 = DuplicateTokenEx(v6, 0x2Cu, 0, SecurityImpersonation, TokenImpersonation, &Token);
    if ( v5 )
    {
      v5 = AdjustTokenPrivileges(Token, 0, &NewState, 0, 0, 0);
      if ( v5 )
        v5 = SetThreadToken(0, Token);
      CloseHandle(Token);
      if ( v5 )
      {
        if ( v7 != -1 )
          return v7;
LABEL_23:
        if ( TokenHandle != (HANDLE)-1LL )
          CloseHandle(TokenHandle);
        if ( v5 )
          return 0;
        return v7;
      }
    }
LABEL_22:
    v7 = -1;
    goto LABEL_23;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids, LastError);
  }
  return -1;
}

```

## disassembly

```asm
0x18000e3b4  mov     [rsp-18h+arg_8], rbx
0x18000e3b9  mov     [rsp-18h+arg_10], rdi
0x18000e3be  push    rbp
0x18000e3bf  push    r14
0x18000e3c1  push    r15
0x18000e3c3  mov     rbp, rsp
0x18000e3c6  sub     rsp, 60h
0x18000e3ca  mov     rax, cs:__security_cookie
0x18000e3d1  xor     rax, rsp
0x18000e3d4  mov     [rbp+var_8], rax
0x18000e3d8  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000e3dc  mov     qword ptr [rbp+Luid.LowPart], 0
0x18000e3e4  xorps   xmm0, xmm0
0x18000e3e7  mov     [rbp+TokenHandle], r15
0x18000e3eb  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18000e3ef  mov     rbx, rcx
0x18000e3f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3f9  lea     rdi, WPP_GLOBAL_Control
0x18000e400  lea     r14d, [r15+3]
0x18000e404  cmp     rcx, rdi
0x18000e407  jz      short loc_18000E429
0x18000e409  test    [rcx+1Ch], r14b
0x18000e40d  jz      short loc_18000E429
0x18000e40f  cmp     byte ptr [rcx+19h], 5
0x18000e413  jb      short loc_18000E429
0x18000e415  mov     rcx, [rcx+10h]
0x18000e419  lea     edx, [r15+0Bh]
0x18000e41d  lea     r8, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids
0x18000e424  call    WPP_SF_
0x18000e429  lea     r8, [rbp+Luid]; lpLuid
0x18000e42d  mov     rdx, rbx; lpName
0x18000e430  xor     ecx, ecx; lpSystemName
0x18000e432  call    cs:__imp_LookupPrivilegeValueW
0x18000e438  test    eax, eax
0x18000e43a  jnz     short loc_18000E481
0x18000e43c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e443  cmp     rcx, rdi
0x18000e446  jz      short loc_18000E479
0x18000e448  test    [rcx+1Ch], r14b
0x18000e44c  jz      short loc_18000E479
0x18000e44e  cmp     [rcx+19h], r14b
0x18000e452  jb      short loc_18000E479
0x18000e454  call    cs:__imp_GetLastError
0x18000e45a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e461  lea     r8, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids
0x18000e468  mov     edx, 0Bh
0x18000e46d  mov     r9d, eax
0x18000e470  mov     rcx, [rcx+10h]
0x18000e474  call    WPP_SF_d
0x18000e479  mov     rax, r15
0x18000e47c  jmp     loc_18000E587
0x18000e481  mov     rax, qword ptr [rbp+Luid.LowPart]
0x18000e485  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x18000e489  mov     [rbp+NewState.PrivilegeCount], 1
0x18000e490  mov     [rbp+NewState.Privileges.Attributes], r14d
0x18000e494  call    cs:__imp_GetCurrentThread
0x18000e49a  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000e49e  xor     r8d, r8d; OpenAsSelf
0x18000e4a1  mov     rcx, rax; ThreadHandle
0x18000e4a4  mov     edx, r14d; DesiredAccess
0x18000e4a7  call    cs:__imp_OpenThreadToken
0x18000e4ad  mov     edi, eax
0x18000e4af  test    eax, eax
0x18000e4b1  jz      short loc_18000E4BC
0x18000e4b3  mov     rcx, [rbp+TokenHandle]
0x18000e4b7  mov     rbx, rcx
0x18000e4ba  jmp     short loc_18000E4F0
0x18000e4bc  call    cs:__imp_GetLastError
0x18000e4c2  cmp     eax, 3F0h
0x18000e4c7  jnz     loc_18000E56A
0x18000e4cd  call    cs:__imp_GetCurrentProcess
0x18000e4d3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000e4d7  mov     edx, r14d; DesiredAccess
0x18000e4da  mov     rcx, rax; ProcessHandle
0x18000e4dd  call    cs:__imp_OpenProcessToken
0x18000e4e3  mov     edi, eax
0x18000e4e5  mov     rbx, r15
0x18000e4e8  test    eax, eax
0x18000e4ea  jz      short loc_18000E56A
0x18000e4ec  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x18000e4f0  xor     r8d, r8d; lpTokenAttributes
0x18000e4f3  mov     [rbp+Token], 0
0x18000e4fb  lea     rax, [rbp+Token]
0x18000e4ff  mov     r9d, r14d; ImpersonationLevel
0x18000e502  mov     [rsp+60h+phNewToken], rax; phNewToken
0x18000e507  mov     [rsp+60h+TokenType], r14d; TokenType
0x18000e50c  lea     edx, [r8+2Ch]; dwDesiredAccess
0x18000e510  call    cs:__imp_DuplicateTokenEx
0x18000e516  mov     edi, eax
0x18000e518  test    eax, eax
0x18000e51a  jz      short loc_18000E56A
0x18000e51c  mov     rcx, [rbp+Token]; TokenHandle
0x18000e520  lea     r8, [rbp+NewState]; NewState
0x18000e524  mov     [rsp+60h+phNewToken], 0; ReturnLength
0x18000e52d  xor     r9d, r9d; BufferLength
0x18000e530  xor     edx, edx; DisableAllPrivileges
0x18000e532  mov     qword ptr [rsp+60h+TokenType], 0; PreviousState
0x18000e53b  call    cs:__imp_AdjustTokenPrivileges
0x18000e541  mov     edi, eax
0x18000e543  test    eax, eax
0x18000e545  jz      short loc_18000E555
0x18000e547  mov     rdx, [rbp+Token]; Token
0x18000e54b  xor     ecx, ecx; Thread
0x18000e54d  call    cs:__imp_SetThreadToken
0x18000e553  mov     edi, eax
0x18000e555  mov     rcx, [rbp+Token]; hObject
0x18000e559  call    cs:__imp_CloseHandle
0x18000e55f  test    edi, edi
0x18000e561  jz      short loc_18000E56A
0x18000e563  cmp     rbx, r15
0x18000e566  jnz     short loc_18000E584
0x18000e568  jmp     short loc_18000E56D
0x18000e56a  mov     rbx, r15
0x18000e56d  mov     rcx, [rbp+TokenHandle]; hObject
0x18000e571  cmp     rcx, r15
0x18000e574  jz      short loc_18000E57C
0x18000e576  call    cs:__imp_CloseHandle
0x18000e57c  xor     ecx, ecx
0x18000e57e  test    edi, edi
0x18000e580  cmovnz  rbx, rcx
0x18000e584  mov     rax, rbx
0x18000e587  mov     rcx, [rbp+var_8]
0x18000e58b  xor     rcx, rsp; StackCookie
0x18000e58e  call    __security_check_cookie
0x18000e593  lea     r11, [rsp+60h+var_s0]
0x18000e598  mov     rbx, [r11+28h]
0x18000e59c  mov     rdi, [r11+30h]
0x18000e5a0  mov     rsp, r11
0x18000e5a3  pop     r15
0x18000e5a5  pop     r14
0x18000e5a7  pop     rbp
0x18000e5a8  retn
```
