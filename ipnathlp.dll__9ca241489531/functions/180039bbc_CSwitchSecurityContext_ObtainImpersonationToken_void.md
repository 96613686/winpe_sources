# CSwitchSecurityContext::ObtainImpersonationToken(void)

- ea: `0x180039bbc`
- end: `0x180039c47`
- name: `?ObtainImpersonationToken@CSwitchSecurityContext@@SAJXZ`
- size: `139`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013b78`

## callees

- `0x180039bbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039be9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039be9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c25`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180039bde`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180039bde`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180039bcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180039bcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039c1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039c1d`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180039c0e`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180039c0e`

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
0x180039bbc  push    rbx
0x180039bbe  sub     rsp, 20h
0x180039bc2  mov     [rsp+28h+TokenHandle], 0
0x180039bcb  call    cs:__imp_GetCurrentProcess
0x180039bd1  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180039bd6  mov     edx, 0Ah; DesiredAccess
0x180039bdb  mov     rcx, rax; ProcessHandle
0x180039bde  call    cs:__imp_OpenProcessToken
0x180039be4  cmp     eax, 1
0x180039be7  jz      short loc_180039BFD
0x180039be9  call    cs:__imp_GetLastError
0x180039bef  mov     ebx, eax
0x180039bf1  test    eax, eax
0x180039bf3  jg      short loc_180039C3C
0x180039bf5  mov     eax, ebx
0x180039bf7  add     rsp, 20h
0x180039bfb  pop     rbx
0x180039bfc  retn
0x180039bfd  mov     rcx, [rsp+28h+TokenHandle]; ExistingTokenHandle
0x180039c02  lea     r8, ?m_hImpersonationToken@CSwitchSecurityContext@@0PEAXEA; DuplicateTokenHandle
0x180039c09  xor     ebx, ebx
0x180039c0b  lea     edx, [rbx+2]; ImpersonationLevel
0x180039c0e  call    cs:__imp_DuplicateToken
0x180039c14  test    eax, eax
0x180039c16  jz      short loc_180039C25
0x180039c18  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180039c1d  call    cs:__imp_CloseHandle
0x180039c23  jmp     short loc_180039BF5
0x180039c25  call    cs:__imp_GetLastError
0x180039c2b  mov     ebx, eax
0x180039c2d  test    eax, eax
0x180039c2f  jle     short loc_180039C18
0x180039c31  movzx   ebx, ax
0x180039c34  or      ebx, 80070000h
0x180039c3a  jmp     short loc_180039C18
0x180039c3c  movzx   ebx, ax
0x180039c3f  or      ebx, 80070000h
0x180039c45  jmp     short loc_180039BF5
```
