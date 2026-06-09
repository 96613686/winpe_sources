# CertSrv::CEventLog::GetUserToken(_TOKEN_USER * *)

- ea: `0x180029844`
- end: `0x180029935`
- name: `?GetUserToken@CEventLog@CertSrv@@AEAAJPEAPEAU_TOKEN_USER@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(CertSrv::CEventLog *__hidden this, struct _TOKEN_USER **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002993c`

## callees

- `0x180021438`
- `0x180029844`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800298c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800298c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002990b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002990b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029922`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029922`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800298a8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800298f7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800298a8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800298f7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180029879`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180029879`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180029866`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180029866`

## pseudocode

```c
__int64 __fastcall CertSrv::CEventLog::GetUserToken(CertSrv::CEventLog *this, struct _TOKEN_USER **a2)
{
  HANDLE CurrentProcess; // rax
  unsigned int v4; // ebx
  struct _TOKEN_USER *v5; // rdi
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  int v8; // [rsp+44h] [rbp+Ch]
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v8 = HIDWORD(this);
  TokenHandle = 0;
  TokenInformationLength = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xF01FFu, &TokenHandle)
    && (GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() == 122) )
  {
    v5 = (struct _TOKEN_USER *)LocalAlloc(0x40u, TokenInformationLength);
    if ( v5 )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
      {
        *a2 = v5;
        v4 = 0;
      }
      else
      {
        v4 = myHLastError();
        LocalFree(v5);
      }
    }
    else
    {
      v4 = -2147024882;
    }
  }
  else
  {
    v4 = myHLastError();
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v4;
}

```

## disassembly

```asm
0x180029844  mov     rax, rsp
0x180029847  mov     [rax+10h], rbx
0x18002984b  mov     [rax+8], rcx
0x18002984f  push    rdi
0x180029850  sub     rsp, 30h
0x180029854  mov     rbx, rdx
0x180029857  mov     qword ptr [rax+18h], 0
0x18002985f  mov     dword ptr [rax+8], 0
0x180029866  call    cs:__imp_GetCurrentProcess
0x18002986c  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180029871  mov     edx, 0F01FFh; DesiredAccess
0x180029876  mov     rcx, rax; ProcessHandle
0x180029879  call    cs:__imp_OpenProcessToken
0x18002987f  test    eax, eax
0x180029881  jnz     short loc_18002988F
0x180029883  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180029888  mov     ebx, eax
0x18002988a  jmp     loc_180029918
0x18002988f  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180029894  lea     rax, [rsp+38h+TokenInformationLength]
0x180029899  xor     r9d, r9d; TokenInformationLength
0x18002989c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800298a1  xor     r8d, r8d; TokenInformation
0x1800298a4  lea     edx, [r9+1]; TokenInformationClass
0x1800298a8  call    cs:__imp_GetTokenInformation
0x1800298ae  test    eax, eax
0x1800298b0  jnz     short loc_1800298BD
0x1800298b2  call    cs:__imp_GetLastError
0x1800298b8  cmp     eax, 7Ah ; 'z'
0x1800298bb  jnz     short loc_180029883
0x1800298bd  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x1800298c1  mov     ecx, 40h ; '@'; uFlags
0x1800298c6  call    cs:__imp_LocalAlloc
0x1800298cc  mov     rdi, rax
0x1800298cf  test    rax, rax
0x1800298d2  jnz     short loc_1800298DB
0x1800298d4  mov     ebx, 8007000Eh
0x1800298d9  jmp     short loc_180029918
0x1800298db  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800298e0  lea     rax, [rsp+38h+TokenInformationLength]
0x1800298e5  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800298ea  mov     r8, rdi; TokenInformation
0x1800298ed  mov     edx, 1; TokenInformationClass
0x1800298f2  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800298f7  call    cs:__imp_GetTokenInformation
0x1800298fd  test    eax, eax
0x1800298ff  jnz     short loc_180029913
0x180029901  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180029906  mov     rcx, rdi; hMem
0x180029909  mov     ebx, eax
0x18002990b  call    cs:__imp_LocalFree
0x180029911  jmp     short loc_180029918
0x180029913  mov     [rbx], rdi
0x180029916  xor     ebx, ebx
0x180029918  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18002991d  test    rcx, rcx
0x180029920  jz      short loc_180029928
0x180029922  call    cs:__imp_CloseHandle
0x180029928  mov     eax, ebx
0x18002992a  mov     rbx, [rsp+38h+arg_8]
0x18002992f  add     rsp, 30h
0x180029933  pop     rdi
0x180029934  retn
```
