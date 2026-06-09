# ModifyTokenPrivileges(void)

- ea: `0x1400031e0`
- end: `0x14000334a`
- name: `?ModifyTokenPrivileges@@YAJXZ`
- size: `362`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000215c`

## callees

- `0x140002e6c`
- `0x1400031e0`
- `0x140005530`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000321c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400032bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000321c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400032bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000323e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400032ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000323e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400032ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140003222`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140003222`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140003234`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140003234`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003325`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003325`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1400032e5`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1400032e5`

## pseudocode

```c
__int64 ModifyTokenPrivileges(void)
{
  HANDLE CurrentProcess; // rax
  signed int v1; // eax
  signed int v2; // ebx
  signed int LastError; // eax
  unsigned int PreviousState; // [rsp+20h] [rbp-60h]
  void *TokenHandle; // [rsp+30h] [rbp-50h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-48h] BYREF
  _OWORD v8[2]; // [rsp+48h] [rbp-38h] BYREF
  int v9; // [rsp+68h] [rbp-18h]

  TokenHandle = 0;
  NewState = 0;
  v9 = 0;
  memset(v8, 0, sizeof(v8));
  SetLastError(0);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20u, &TokenHandle) )
  {
    NewState.PrivilegeCount = 4;
    NewState.Privileges[0].Attributes = 2;
    DWORD2(v8[0]) = 2;
    DWORD1(v8[1]) = 2;
    v9 = 2;
    NewState.Privileges[0].Luid = (LUID)30LL;
    *(_QWORD *)&v8[0] = 23;
    *(_QWORD *)((char *)v8 + 12) = 33;
    *((_QWORD *)&v8[1] + 1) = 14;
    SetLastError(0);
    if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x34u, 0, 0) )
    {
      v2 = 0;
      goto LABEL_13;
    }
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    PreviousState = 77;
  }
  else
  {
    v1 = GetLastError();
    v2 = v1;
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
    PreviousState = 60;
  }
  if ( v2 >= 0 )
    v2 = -2003304445;
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v2, PreviousState, 0);
LABEL_13:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400031e0  mov     [rsp-8+arg_0], rbx
0x1400031e5  push    rbp
0x1400031e6  mov     rbp, rsp
0x1400031e9  sub     rsp, 80h
0x1400031f0  mov     rax, cs:__security_cookie
0x1400031f7  xor     rax, rsp
0x1400031fa  mov     [rbp+var_10], rax
0x1400031fe  xorps   xmm0, xmm0
0x140003201  mov     [rbp+TokenHandle], 0
0x140003209  xor     eax, eax
0x14000320b  xor     ecx, ecx; dwErrCode
0x14000320d  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x140003211  mov     [rbp+var_18], eax
0x140003214  movups  [rbp+var_38], xmm0
0x140003218  movups  [rbp+var_28], xmm0
0x14000321c  call    cs:__imp_SetLastError
0x140003222  call    cs:__imp_GetCurrentProcess
0x140003228  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14000322c  mov     edx, 20h ; ' '; DesiredAccess
0x140003231  mov     rcx, rax; ProcessHandle
0x140003234  call    cs:__imp_OpenProcessToken
0x14000323a  test    eax, eax
0x14000323c  jnz     short loc_140003283
0x14000323e  call    cs:__imp_GetLastError
0x140003244  mov     ebx, eax
0x140003246  test    eax, eax
0x140003248  jle     short loc_140003253
0x14000324a  movzx   ebx, ax
0x14000324d  or      ebx, 80070000h
0x140003253  mov     [rsp+80h+ReturnLength], 0; void *
0x14000325c  mov     dword ptr [rsp+80h+PreviousState], 3Ch ; '<'; unsigned int
0x140003264  test    ebx, ebx
0x140003266  mov     eax, 88980003h
0x14000326b  cmovns  ebx, eax
0x14000326e  xor     edx, edx; int *
0x140003270  mov     r9d, ebx; int
0x140003273  xor     r8d, r8d; unsigned int
0x140003276  lea     ecx, [rdx+14h]; unsigned int
0x140003279  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x14000327e  jmp     loc_14000331C
0x140003283  mov     eax, 2
0x140003288  mov     [rbp+NewState.PrivilegeCount], 4
0x14000328f  xor     ecx, ecx; dwErrCode
0x140003291  mov     [rbp+NewState.Privileges.Attributes], eax
0x140003294  mov     dword ptr [rbp+var_38+8], eax
0x140003297  mov     dword ptr [rbp+var_28+4], eax
0x14000329a  mov     [rbp+var_18], eax
0x14000329d  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 1Eh
0x1400032a5  mov     qword ptr [rbp+var_38], 17h
0x1400032ad  mov     qword ptr [rbp+var_38+0Ch], 21h ; '!'
0x1400032b5  mov     qword ptr [rbp+var_28+8], 0Eh
0x1400032bd  call    cs:__imp_SetLastError
0x1400032c3  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400032c7  lea     r8, [rbp+NewState]; NewState
0x1400032cb  mov     r9d, 34h ; '4'; BufferLength
0x1400032d1  mov     [rsp+80h+ReturnLength], 0; ReturnLength
0x1400032da  xor     edx, edx; DisableAllPrivileges
0x1400032dc  mov     [rsp+80h+PreviousState], 0; PreviousState
0x1400032e5  call    cs:__imp_AdjustTokenPrivileges
0x1400032eb  test    eax, eax
0x1400032ed  jnz     short loc_14000331A
0x1400032ef  call    cs:__imp_GetLastError
0x1400032f5  mov     ebx, eax
0x1400032f7  test    eax, eax
0x1400032f9  jle     short loc_140003304
0x1400032fb  movzx   ebx, ax
0x1400032fe  or      ebx, 80070000h
0x140003304  mov     [rsp+80h+ReturnLength], 0
0x14000330d  mov     dword ptr [rsp+80h+PreviousState], 4Dh ; 'M'
0x140003315  jmp     loc_140003264
0x14000331a  xor     ebx, ebx
0x14000331c  mov     rcx, [rbp+TokenHandle]; hObject
0x140003320  test    rcx, rcx
0x140003323  jz      short loc_14000332B
0x140003325  call    cs:__imp_CloseHandle
0x14000332b  mov     eax, ebx
0x14000332d  mov     rcx, [rbp+var_10]
0x140003331  xor     rcx, rsp; StackCookie
0x140003334  call    __security_check_cookie
0x140003339  mov     rbx, [rsp+80h+arg_0]
0x140003341  add     rsp, 80h
0x140003348  pop     rbp
0x140003349  retn
```
