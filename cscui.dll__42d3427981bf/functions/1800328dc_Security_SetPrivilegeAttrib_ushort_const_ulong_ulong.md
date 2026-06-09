# Security_SetPrivilegeAttrib(ushort const *,ulong,ulong *)

- ea: `0x1800328dc`
- end: `0x1800329e6`
- name: `?Security_SetPrivilegeAttrib@@YAKPEBGKPEAK@Z`
- size: `266`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010f40`

## callees

- `0x1800328dc`
- `0x18004c670`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003293d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003293d`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003299c`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003299c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003295a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003295a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032948`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032948`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800329aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800329c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800329aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800329c0`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180032933`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180032933`

## string_xrefs

- `0x180032922`: `SeShutdownPrivilege`

## pseudocode

```c
DWORD __fastcall Security_SetPrivilegeAttrib(const unsigned __int16 *a1, DWORD a2, unsigned int *a3)
{
  HANDLE CurrentProcess; // rax
  DWORD ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  _LUID Luid; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+58h] [rbp-18h] BYREF

  Luid = 0;
  ReturnLength = 0;
  TokenHandle = 0;
  NewState = 0;
  PreviousState = 0;
  if ( !LookupPrivilegeValueW(0, L"SeShutdownPrivilege", &Luid) )
    return GetLastError();
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    return GetLastError();
  NewState.Privileges[0].Luid = Luid;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = a2;
  ReturnLength = 16;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength) )
  {
    CloseHandle(TokenHandle);
    return GetLastError();
  }
  if ( a3 )
    *a3 = PreviousState.Privileges[0].Attributes;
  CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x1800328dc  mov     [rsp-8+arg_0], rbx
0x1800328e1  mov     [rsp-8+arg_8], rdi
0x1800328e6  push    rbp
0x1800328e7  mov     rbp, rsp
0x1800328ea  sub     rsp, 70h
0x1800328ee  mov     rax, cs:__security_cookie
0x1800328f5  xor     rax, rsp
0x1800328f8  mov     [rbp+var_8], rax
0x1800328fc  mov     rbx, r8
0x1800328ff  mov     qword ptr [rbp+Luid.LowPart], 0
0x180032907  mov     edi, edx
0x180032909  mov     [rbp+var_40], 0
0x180032910  xorps   xmm0, xmm0
0x180032913  mov     [rbp+TokenHandle], 0
0x18003291b  xorps   xmm1, xmm1
0x18003291e  lea     r8, [rbp+Luid]; lpLuid
0x180032922  lea     rdx, Name; "SeShutdownPrivilege"
0x180032929  xor     ecx, ecx; lpSystemName
0x18003292b  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18003292f  movups  xmmword ptr [rbp+var_18.PrivilegeCount], xmm1
0x180032933  call    cs:__imp_LookupPrivilegeValueW
0x180032939  test    eax, eax
0x18003293b  jnz     short loc_180032948
0x18003293d  call    cs:__imp_GetLastError
0x180032943  jmp     loc_1800329C8
0x180032948  call    cs:__imp_GetCurrentProcess
0x18003294e  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180032952  mov     edx, 28h ; '('; DesiredAccess
0x180032957  mov     rcx, rax; ProcessHandle
0x18003295a  call    cs:__imp_OpenProcessToken
0x180032960  test    eax, eax
0x180032962  jz      short loc_18003293D
0x180032964  mov     rax, qword ptr [rbp+Luid.LowPart]
0x180032968  lea     r8, [rbp+NewState]; NewState
0x18003296c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180032970  mov     r9d, 10h; BufferLength
0x180032976  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x18003297a  xor     edx, edx; DisableAllPrivileges
0x18003297c  lea     rax, [rbp+var_40]
0x180032980  mov     [rbp+NewState.PrivilegeCount], 1
0x180032987  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003298c  lea     rax, [rbp+var_18]
0x180032990  mov     [rsp+70h+PreviousState], rax; PreviousState
0x180032995  mov     [rbp+NewState.Privileges.Attributes], edi
0x180032998  mov     [rbp+var_40], r9d
0x18003299c  call    cs:__imp_AdjustTokenPrivileges
0x1800329a2  test    eax, eax
0x1800329a4  jnz     short loc_1800329B2
0x1800329a6  mov     rcx, [rbp+TokenHandle]; hObject
0x1800329aa  call    cs:__imp_CloseHandle
0x1800329b0  jmp     short loc_18003293D
0x1800329b2  test    rbx, rbx
0x1800329b5  jz      short loc_1800329BC
0x1800329b7  mov     eax, [rbp+var_18.Privileges.Attributes]
0x1800329ba  mov     [rbx], eax
0x1800329bc  mov     rcx, [rbp+TokenHandle]; hObject
0x1800329c0  call    cs:__imp_CloseHandle
0x1800329c6  xor     eax, eax
0x1800329c8  mov     rcx, [rbp+var_8]
0x1800329cc  xor     rcx, rsp; StackCookie
0x1800329cf  call    __security_check_cookie
0x1800329d4  lea     r11, [rsp+70h+var_s0]
0x1800329d9  mov     rbx, [r11+10h]
0x1800329dd  mov     rdi, [r11+18h]
0x1800329e1  mov     rsp, r11
0x1800329e4  pop     rbp
0x1800329e5  retn
```
