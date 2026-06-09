# CBackupSession::CreateEventListenerToken(void)

- ea: `0x18001768c`
- end: `0x180017893`
- name: `?CreateEventListenerToken@CBackupSession@@AEAAJXZ`
- size: `519`
- prototype: `__int64 __fastcall(CBackupSession *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019dd0`

## callees

- `0x180007818`
- `0x18001768c`
- `0x180031680`

## import_xrefs

- `ADVAPI32!AdjustTokenPrivileges` at `0x180017814`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180017814`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18001779e`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18001779e`
- `ADVAPI32!DuplicateTokenEx` at `0x180017747`
- `ADVAPI32!DuplicateTokenEx` at `0x180017747`
- `ADVAPI32!OpenProcessToken` at `0x1800176d8`
- `ADVAPI32!OpenProcessToken` at `0x1800176d8`
- `KERNEL32!GetLastError` at `0x1800176e2`
- `KERNEL32!GetLastError` at `0x180017751`
- `KERNEL32!GetLastError` at `0x1800177a8`
- `KERNEL32!GetLastError` at `0x18001781e`
- `KERNEL32!GetLastError` at `0x1800176e2`
- `KERNEL32!GetLastError` at `0x180017751`
- `KERNEL32!GetLastError` at `0x1800177a8`
- `KERNEL32!GetLastError` at `0x18001781e`
- `KERNEL32!CloseHandle` at `0x18001786d`
- `KERNEL32!CloseHandle` at `0x18001786d`
- `KERNEL32!GetCurrentProcess` at `0x1800176c6`
- `KERNEL32!GetCurrentProcess` at `0x1800176c6`

## string_xrefs

- `0x180017797`: `SeBackupPrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=3
__int64 __fastcall CBackupSession::CreateEventListenerToken(CBackupSession *this)
{
  HANDLE CurrentProcess; // rax
  signed int v3; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  void **phNewToken; // rdi
  signed int v8; // eax
  signed int v9; // eax
  void *v10; // rcx
  signed int LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  _LUID Luid; // [rsp+38h] [rbp-28h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-20h] BYREF

  Luid = 0;
  NewState = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
  {
    phNewToken = (void **)((char *)this + 392);
    if ( DuplicateTokenEx(TokenHandle, 0x2Cu, 0, SecurityImpersonation, TokenImpersonation, phNewToken) )
    {
      if ( LookupPrivilegeValueW(0, L"SeBackupPrivilege", &Luid) )
      {
        v10 = *phNewToken;
        v4 = 0;
        NewState.PrivilegeCount = 1;
        NewState.Privileges[0].Luid = Luid;
        NewState.Privileges[0].Attributes = 2;
        if ( !AdjustTokenPrivileges(v10, 0, &NewState, 0x10u, 0, 0) )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 84;
            goto LABEL_25;
          }
        }
      }
      else
      {
        v9 = GetLastError();
        v4 = v9;
        if ( v9 > 0 )
          v4 = (unsigned __int16)v9 | 0x80070000;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 83;
          goto LABEL_25;
        }
      }
    }
    else
    {
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 82;
        goto LABEL_25;
      }
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 81;
LABEL_25:
      WPP_SF_d(v5[2], v6, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, v4);
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v4;
}

```

## disassembly

```asm
0x18001768c  mov     [rsp-8+arg_8], rbx
0x180017691  mov     [rsp-8+arg_10], rdi
0x180017696  push    rbp
0x180017697  mov     rbp, rsp
0x18001769a  sub     rsp, 60h
0x18001769e  mov     rax, cs:__security_cookie
0x1800176a5  xor     rax, rsp
0x1800176a8  mov     [rbp+var_10], rax
0x1800176ac  xorps   xmm0, xmm0
0x1800176af  mov     qword ptr [rbp+Luid.LowPart], 0
0x1800176b7  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x1800176bb  mov     rdi, rcx
0x1800176be  mov     [rbp+TokenHandle], 0
0x1800176c6  call    cs:__imp_GetCurrentProcess
0x1800176cc  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800176d0  mov     edx, 0Ah; DesiredAccess
0x1800176d5  mov     rcx, rax; ProcessHandle
0x1800176d8  call    cs:__imp_OpenProcessToken
0x1800176de  test    eax, eax
0x1800176e0  jnz     short loc_180017722
0x1800176e2  call    cs:__imp_GetLastError
0x1800176e8  mov     ebx, eax
0x1800176ea  test    eax, eax
0x1800176ec  jle     short loc_1800176F7
0x1800176ee  movzx   ebx, ax
0x1800176f1  or      ebx, 80070000h
0x1800176f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800176fe  lea     rax, WPP_GLOBAL_Control
0x180017705  cmp     rcx, rax
0x180017708  jz      loc_180017864
0x18001770e  test    byte ptr [rcx+1Ch], 1
0x180017712  jz      loc_180017864
0x180017718  mov     edx, 51h ; 'Q'
0x18001771d  jmp     loc_180017851
0x180017722  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180017726  mov     r9d, 2; ImpersonationLevel
0x18001772c  add     rdi, 188h
0x180017733  xor     r8d, r8d; lpTokenAttributes
0x180017736  mov     [rsp+60h+phNewToken], rdi; phNewToken
0x18001773b  mov     [rsp+60h+TokenType], 2; TokenType
0x180017743  lea     edx, [r9+2Ah]; dwDesiredAccess
0x180017747  call    cs:__imp_DuplicateTokenEx
0x18001774d  test    eax, eax
0x18001774f  jnz     short loc_180017791
0x180017751  call    cs:__imp_GetLastError
0x180017757  mov     ebx, eax
0x180017759  test    eax, eax
0x18001775b  jle     short loc_180017766
0x18001775d  movzx   ebx, ax
0x180017760  or      ebx, 80070000h
0x180017766  mov     rcx, cs:WPP_GLOBAL_Control
0x18001776d  lea     rax, WPP_GLOBAL_Control
0x180017774  cmp     rcx, rax
0x180017777  jz      loc_180017864
0x18001777d  test    byte ptr [rcx+1Ch], 1
0x180017781  jz      loc_180017864
0x180017787  mov     edx, 52h ; 'R'
0x18001778c  jmp     loc_180017851
0x180017791  lea     r8, [rbp+Luid]; lpLuid
0x180017795  xor     ecx, ecx; lpSystemName
0x180017797  lea     rdx, Name; "SeBackupPrivilege"
0x18001779e  call    cs:__imp_LookupPrivilegeValueW
0x1800177a4  test    eax, eax
0x1800177a6  jnz     short loc_1800177E5
0x1800177a8  call    cs:__imp_GetLastError
0x1800177ae  mov     ebx, eax
0x1800177b0  test    eax, eax
0x1800177b2  jle     short loc_1800177BD
0x1800177b4  movzx   ebx, ax
0x1800177b7  or      ebx, 80070000h
0x1800177bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177c4  lea     rax, WPP_GLOBAL_Control
0x1800177cb  cmp     rcx, rax
0x1800177ce  jz      loc_180017864
0x1800177d4  test    byte ptr [rcx+1Ch], 1
0x1800177d8  jz      loc_180017864
0x1800177de  mov     edx, 53h ; 'S'
0x1800177e3  jmp     short loc_180017851
0x1800177e5  mov     rax, qword ptr [rbp+Luid.LowPart]
0x1800177e9  lea     r8, [rbp+NewState]; NewState
0x1800177ed  mov     rcx, [rdi]; TokenHandle
0x1800177f0  xor     ebx, ebx
0x1800177f2  mov     [rsp+60h+phNewToken], rbx; ReturnLength
0x1800177f7  xor     edx, edx; DisableAllPrivileges
0x1800177f9  mov     [rbp+NewState.PrivilegeCount], 1
0x180017800  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x180017804  lea     r9d, [rbx+10h]; BufferLength
0x180017808  mov     [rbp+NewState.Privileges.Attributes], 2
0x18001780f  mov     qword ptr [rsp+60h+TokenType], rbx; PreviousState
0x180017814  call    cs:__imp_AdjustTokenPrivileges
0x18001781a  test    eax, eax
0x18001781c  jnz     short loc_180017864
0x18001781e  call    cs:__imp_GetLastError
0x180017824  mov     ebx, eax
0x180017826  test    eax, eax
0x180017828  jle     short loc_180017833
0x18001782a  movzx   ebx, ax
0x18001782d  or      ebx, 80070000h
0x180017833  mov     rcx, cs:WPP_GLOBAL_Control
0x18001783a  lea     rax, WPP_GLOBAL_Control
0x180017841  cmp     rcx, rax
0x180017844  jz      short loc_180017864
0x180017846  test    byte ptr [rcx+1Ch], 1
0x18001784a  jz      short loc_180017864
0x18001784c  mov     edx, 54h ; 'T'
0x180017851  mov     rcx, [rcx+10h]
0x180017855  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001785c  mov     r9d, ebx
0x18001785f  call    WPP_SF_d
0x180017864  mov     rcx, [rbp+TokenHandle]; hObject
0x180017868  test    rcx, rcx
0x18001786b  jz      short loc_180017873
0x18001786d  call    cs:__imp_CloseHandle
0x180017873  mov     eax, ebx
0x180017875  mov     rcx, [rbp+var_10]
0x180017879  xor     rcx, rsp; StackCookie
0x18001787c  call    __security_check_cookie
0x180017881  lea     r11, [rsp+60h+var_s0]
0x180017886  mov     rbx, [r11+18h]
0x18001788a  mov     rdi, [r11+20h]
0x18001788e  mov     rsp, r11
0x180017891  pop     rbp
0x180017892  retn
```
