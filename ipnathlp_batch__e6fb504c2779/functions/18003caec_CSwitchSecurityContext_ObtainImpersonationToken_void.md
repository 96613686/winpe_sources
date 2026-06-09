# CSwitchSecurityContext::ObtainImpersonationToken(void)

- ea: `0x18003caec`
- end: `0x18003cb9c`
- name: `?ObtainImpersonationToken@CSwitchSecurityContext@@SAJXZ`
- size: `176`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014b7c`

## callees

- `0x18003caec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb74`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003cb14`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003cb14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003cafb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003cafb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cb66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cb66`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18003cb51`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18003cb51`

## pseudocode

```c
__int64 CSwitchSecurityContext::ObtainImpersonationToken(void)
{
  HANDLE CurrentProcess; // rax
  signed int v1; // eax
  unsigned int v2; // ebx
  signed int LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
  {
    v2 = 0;
    if ( !DuplicateToken(TokenHandle, SecurityImpersonation, &CSwitchSecurityContext::m_hImpersonationToken) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(TokenHandle);
  }
  else
  {
    v1 = GetLastError();
    v2 = v1;
    if ( v1 > 0 )
      return (unsigned __int16)v1 | 0x80070000;
  }
  return v2;
}

```

## disassembly

```asm
0x18003caec  push    rbx
0x18003caee  sub     rsp, 20h
0x18003caf2  mov     [rsp+28h+TokenHandle], 0
0x18003cafb  call    cs:__imp_GetCurrentProcess
0x18003cb02  nop     dword ptr [rax+rax+00h]
0x18003cb07  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18003cb0c  mov     edx, 0Ah; DesiredAccess
0x18003cb11  mov     rcx, rax; ProcessHandle
0x18003cb14  call    cs:__imp_OpenProcessToken
0x18003cb1b  nop     dword ptr [rax+rax+00h]
0x18003cb20  cmp     eax, 1
0x18003cb23  jz      short loc_18003CB40
0x18003cb25  call    cs:__imp_GetLastError
0x18003cb2c  nop     dword ptr [rax+rax+00h]
0x18003cb31  mov     ebx, eax
0x18003cb33  test    eax, eax
0x18003cb35  jg      short loc_18003CB91
0x18003cb37  mov     eax, ebx
0x18003cb39  add     rsp, 20h
0x18003cb3d  pop     rbx
0x18003cb3e  retn
0x18003cb40  mov     rcx, [rsp+28h+TokenHandle]; ExistingTokenHandle
0x18003cb45  lea     r8, ?m_hImpersonationToken@CSwitchSecurityContext@@0PEAXEA; DuplicateTokenHandle
0x18003cb4c  xor     ebx, ebx
0x18003cb4e  lea     edx, [rbx+2]; ImpersonationLevel
0x18003cb51  call    cs:__imp_DuplicateToken
0x18003cb58  nop     dword ptr [rax+rax+00h]
0x18003cb5d  test    eax, eax
0x18003cb5f  jz      short loc_18003CB74
0x18003cb61  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18003cb66  call    cs:__imp_CloseHandle
0x18003cb6d  nop     dword ptr [rax+rax+00h]
0x18003cb72  jmp     short loc_18003CB37
0x18003cb74  call    cs:__imp_GetLastError
0x18003cb7b  nop     dword ptr [rax+rax+00h]
0x18003cb80  mov     ebx, eax
0x18003cb82  test    eax, eax
0x18003cb84  jle     short loc_18003CB61
0x18003cb86  movzx   ebx, ax
0x18003cb89  or      ebx, 80070000h
0x18003cb8f  jmp     short loc_18003CB61
0x18003cb91  movzx   ebx, ax
0x18003cb94  or      ebx, 80070000h
0x18003cb9a  jmp     short loc_18003CB37
```
