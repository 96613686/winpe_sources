# RegAdjustTokenPrivileges

- ea: `0x140004450`
- end: `0x140004510`
- name: `RegAdjustTokenPrivileges`
- size: `192`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003ec4`
- `0x140004518`
- `0x140004708`
- `0x140004a38`

## callees

- `0x140001340`
- `0x140004450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004496`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000448c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000448c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140004479`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140004479`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400044ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400044f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400044ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400044f5`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1400044de`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1400044de`

## pseudocode

```c
DWORD __fastcall RegAdjustTokenPrivileges(int a1)
{
  LUID v1; // rbx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF

  v1 = (LUID)a1;
  NewState = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    return GetLastError();
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = v1;
  NewState.Privileges[0].Attributes = 2;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
  {
    CloseHandle(TokenHandle);
    return GetLastError();
  }
  CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x140004450  push    rbx
0x140004452  sub     rsp, 50h
0x140004456  mov     rax, cs:__security_cookie
0x14000445d  xor     rax, rsp
0x140004460  mov     [rsp+58h+var_10], rax
0x140004465  xorps   xmm0, xmm0
0x140004468  movsxd  rbx, ecx
0x14000446b  movups  xmmword ptr [rsp+58h+NewState.PrivilegeCount], xmm0
0x140004470  mov     [rsp+58h+TokenHandle], 0
0x140004479  call    cs:__imp_GetCurrentProcess
0x14000447f  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x140004484  mov     edx, 28h ; '('; DesiredAccess
0x140004489  mov     rcx, rax; ProcessHandle
0x14000448c  call    cs:__imp_OpenProcessToken
0x140004492  test    eax, eax
0x140004494  jnz     short loc_14000449E
0x140004496  call    cs:__imp_GetLastError
0x14000449c  jmp     short loc_1400044FD
0x14000449e  mov     rcx, rbx
0x1400044a1  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x1400044aa  shr     rcx, 20h
0x1400044ae  lea     r8, [rsp+58h+NewState]; NewState
0x1400044b3  mov     [rsp+58h+NewState.Privileges.Luid.HighPart], ecx
0x1400044b7  xor     r9d, r9d; BufferLength
0x1400044ba  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x1400044bf  xor     edx, edx; DisableAllPrivileges
0x1400044c1  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x1400044c9  mov     [rsp+58h+NewState.Privileges.Luid.LowPart], ebx
0x1400044cd  mov     [rsp+58h+NewState.Privileges.Attributes], 2
0x1400044d5  mov     [rsp+58h+PreviousState], 0; PreviousState
0x1400044de  call    cs:__imp_AdjustTokenPrivileges
0x1400044e4  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x1400044e9  test    eax, eax
0x1400044eb  jnz     short loc_1400044F5
0x1400044ed  call    cs:__imp_CloseHandle
0x1400044f3  jmp     short loc_140004496
0x1400044f5  call    cs:__imp_CloseHandle
0x1400044fb  xor     eax, eax
0x1400044fd  mov     rcx, [rsp+58h+var_10]
0x140004502  xor     rcx, rsp; StackCookie
0x140004505  call    __security_check_cookie
0x14000450a  add     rsp, 50h
0x14000450e  pop     rbx
0x14000450f  retn
```
