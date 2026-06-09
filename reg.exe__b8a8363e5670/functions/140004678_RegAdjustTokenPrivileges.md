# RegAdjustTokenPrivileges

- ea: `0x140004678`
- end: `0x14000475d`
- name: `RegAdjustTokenPrivileges`
- size: `229`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400040b8`
- `0x140004764`
- `0x14000496c`
- `0x140004cf0`

## callees

- `0x140001340`
- `0x140004678`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400046ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400046ca`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400046ba`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400046ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400046a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400046a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000472d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000473b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000472d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000473b`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140004718`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140004718`

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
0x140004678  push    rbx
0x14000467a  sub     rsp, 50h
0x14000467e  mov     rax, cs:__security_cookie
0x140004685  xor     rax, rsp
0x140004688  mov     [rsp+58h+var_10], rax
0x14000468d  xorps   xmm0, xmm0
0x140004690  movsxd  rbx, ecx
0x140004693  movups  xmmword ptr [rsp+58h+NewState.PrivilegeCount], xmm0
0x140004698  mov     [rsp+58h+TokenHandle], 0
0x1400046a1  call    cs:__imp_GetCurrentProcess
0x1400046a8  nop     dword ptr [rax+rax+00h]
0x1400046ad  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x1400046b2  mov     edx, 28h ; '('; DesiredAccess
0x1400046b7  mov     rcx, rax; ProcessHandle
0x1400046ba  call    cs:__imp_OpenProcessToken
0x1400046c1  nop     dword ptr [rax+rax+00h]
0x1400046c6  test    eax, eax
0x1400046c8  jnz     short loc_1400046D8
0x1400046ca  call    cs:__imp_GetLastError
0x1400046d1  nop     dword ptr [rax+rax+00h]
0x1400046d6  jmp     short loc_140004749
0x1400046d8  mov     rcx, rbx
0x1400046db  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x1400046e4  shr     rcx, 20h
0x1400046e8  lea     r8, [rsp+58h+NewState]; NewState
0x1400046ed  mov     [rsp+58h+NewState.Privileges.Luid.HighPart], ecx
0x1400046f1  xor     r9d, r9d; BufferLength
0x1400046f4  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x1400046f9  xor     edx, edx; DisableAllPrivileges
0x1400046fb  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x140004703  mov     [rsp+58h+NewState.Privileges.Luid.LowPart], ebx
0x140004707  mov     [rsp+58h+NewState.Privileges.Attributes], 2
0x14000470f  mov     [rsp+58h+PreviousState], 0; PreviousState
0x140004718  call    cs:__imp_AdjustTokenPrivileges
0x14000471f  nop     dword ptr [rax+rax+00h]
0x140004724  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x140004729  test    eax, eax
0x14000472b  jnz     short loc_14000473B
0x14000472d  call    cs:__imp_CloseHandle
0x140004734  nop     dword ptr [rax+rax+00h]
0x140004739  jmp     short loc_1400046CA
0x14000473b  call    cs:__imp_CloseHandle
0x140004742  nop     dword ptr [rax+rax+00h]
0x140004747  xor     eax, eax
0x140004749  mov     rcx, [rsp+58h+var_10]
0x14000474e  xor     rcx, rsp; StackCookie
0x140004751  call    __security_check_cookie
0x140004756  add     rsp, 50h
0x14000475a  pop     rbx
0x14000475b  retn
```
