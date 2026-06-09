# EnableDebugPrivilege(void)

- ea: `0x1804153c8`
- end: `0x1804155e3`
- name: `?EnableDebugPrivilege@@YAJXZ`
- size: `539`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801ad2f8`
- `0x18041ead0`
- `0x18041f660`
- `0x180421640`
- `0x180421970`
- `0x1804219f0`
- `0x180421a60`

## callees

- `0x1800f0f40`
- `0x1804153c8`
- `0x1804da4c0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x1804154f3`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x1804154f3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18041558e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18041558e`
- `api-ms-win-crt-environment-l1-1-0!getenv` at `0x180415402`
- `api-ms-win-crt-environment-l1-1-0!getenv` at `0x180415402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804154b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804154c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415570`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804154b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804154c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180415570`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1804154a3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1804154a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18041548a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18041548a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18041559f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18041559f`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExA` at `0x180415420`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExA` at `0x180415420`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180415549`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180415549`

## string_xrefs

- `0x1804153fb`: `DBGENG_NO_DEBUG_PRIVILEGE`

## pseudocode

```c
__int64 EnableDebugPrivilege(void)
{
  unsigned int v0; // ebx
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  signed int v4; // eax
  char *v5; // rax
  void *v6; // rdi
  void *v7; // rcx
  signed int v8; // eax
  void *TokenHandle[2]; // [rsp+30h] [rbp-C8h] BYREF
  _OSVERSIONINFOA VersionInformation; // [rsp+40h] [rbp-B8h] BYREF

  memset(&VersionInformation, 0, sizeof(VersionInformation));
  if ( !getenv("DBGENG_NO_DEBUG_PRIVILEGE") )
  {
    VersionInformation.dwOSVersionInfoSize = 148;
    if ( !GetVersionExA(&VersionInformation) )
    {
      if ( GetLastError() )
      {
        LastError = GetLastError();
        v0 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
        return v0;
      }
      return (unsigned int)-2147467259;
    }
    if ( VersionInformation.dwPlatformId == 2 )
    {
      TokenHandle[0] = 0;
      if ( !byte_1807EC10C )
      {
        CurrentProcess = GetCurrentProcess();
        if ( OpenProcessToken(CurrentProcess, 0x20u, TokenHandle) )
        {
          v5 = (char *)calloc(1u, 0x10u);
          v6 = v5;
          if ( v5 )
          {
            v7 = TokenHandle[0];
            v0 = 0;
            *(_DWORD *)v5 = 1;
            TokenHandle[1] = (void *)20;
            *(_QWORD *)(v5 + 4) = 20;
            *((_DWORD *)v5 + 3) = 2;
            if ( !AdjustTokenPrivileges(v7, 0, (PTOKEN_PRIVILEGES)v5, 0, 0, 0) )
            {
              if ( GetLastError() )
              {
                v8 = GetLastError();
                v0 = v8;
                if ( v8 > 0 )
                  v0 = (unsigned __int16)v8 | 0x80070000;
              }
              else
              {
                v0 = -2147467259;
              }
            }
            free(v6);
          }
          else
          {
            v0 = -2147024882;
          }
          CloseHandle(TokenHandle[0]);
        }
        else
        {
          if ( !GetLastError() )
            return (unsigned int)-2147467259;
          v4 = GetLastError();
          v0 = v4;
          if ( v4 > 0 )
            v0 = (unsigned __int16)v4 | 0x80070000;
        }
        if ( !v0 )
          byte_1807EC10C = 1;
        return v0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1804153c8  mov     [rsp+arg_0], rbx
0x1804153cd  push    rdi
0x1804153ce  sub     rsp, 0F0h
0x1804153d5  mov     rax, cs:__security_cookie
0x1804153dc  xor     rax, rsp
0x1804153df  mov     [rsp+0F8h+var_18], rax
0x1804153e7  mov     ebx, 94h
0x1804153ec  lea     rcx, [rsp+0F8h+VersionInformation]; void *
0x1804153f1  mov     r8d, ebx; Size
0x1804153f4  xor     edx, edx; Val
0x1804153f6  call    memset
0x1804153fb  lea     rcx, aDbgengNoDebugP; "DBGENG_NO_DEBUG_PRIVILEGE"
0x180415402  call    cs:__imp_getenv
0x180415409  nop     dword ptr [rax+rax+00h]
0x18041540e  test    rax, rax
0x180415411  jnz     loc_1804155BF
0x180415417  lea     rcx, [rsp+0F8h+VersionInformation]; lpVersionInformation
0x18041541c  mov     [rsp+0F8h+VersionInformation.dwOSVersionInfoSize], ebx
0x180415420  call    cs:__imp_GetVersionExA
0x180415427  nop     dword ptr [rax+rax+00h]
0x18041542c  test    eax, eax
0x18041542e  jnz     short loc_180415469
0x180415430  call    cs:__imp_GetLastError
0x180415437  nop     dword ptr [rax+rax+00h]
0x18041543c  test    eax, eax
0x18041543e  jnz     short loc_180415447
0x180415440  mov     ebx, 80004005h
0x180415445  jmp     short loc_180415462
0x180415447  call    cs:__imp_GetLastError
0x18041544e  nop     dword ptr [rax+rax+00h]
0x180415453  mov     ebx, eax
0x180415455  test    eax, eax
0x180415457  jle     short loc_180415462
0x180415459  movzx   ebx, ax
0x18041545c  or      ebx, 80070000h
0x180415462  mov     eax, ebx
0x180415464  jmp     loc_1804155C1
0x180415469  cmp     [rsp+0F8h+VersionInformation.dwPlatformId], 2
0x18041546e  jnz     loc_1804155BF
0x180415474  cmp     cs:byte_1807EC10C, 0
0x18041547b  mov     [rsp+0F8h+TokenHandle], 0
0x180415484  jnz     loc_1804155BF
0x18041548a  call    cs:__imp_GetCurrentProcess
0x180415491  nop     dword ptr [rax+rax+00h]
0x180415496  lea     r8, [rsp+0F8h+TokenHandle]; TokenHandle
0x18041549b  mov     edx, 20h ; ' '; DesiredAccess
0x1804154a0  mov     rcx, rax; ProcessHandle
0x1804154a3  call    cs:__imp_OpenProcessToken
0x1804154aa  nop     dword ptr [rax+rax+00h]
0x1804154af  test    eax, eax
0x1804154b1  jnz     short loc_1804154EB
0x1804154b3  call    cs:__imp_GetLastError
0x1804154ba  nop     dword ptr [rax+rax+00h]
0x1804154bf  test    eax, eax
0x1804154c1  jz      loc_180415440
0x1804154c7  call    cs:__imp_GetLastError
0x1804154ce  nop     dword ptr [rax+rax+00h]
0x1804154d3  mov     ebx, eax
0x1804154d5  test    eax, eax
0x1804154d7  jle     loc_1804155AB
0x1804154dd  movzx   ebx, ax
0x1804154e0  or      ebx, 80070000h
0x1804154e6  jmp     loc_1804155AB
0x1804154eb  mov     edx, 10h; Size
0x1804154f0  lea     ecx, [rdx-0Fh]; Count
0x1804154f3  call    cs:__imp_calloc
0x1804154fa  nop     dword ptr [rax+rax+00h]
0x1804154ff  mov     rdi, rax
0x180415502  test    rax, rax
0x180415505  jnz     short loc_180415511
0x180415507  mov     ebx, 8007000Eh
0x18041550c  jmp     loc_18041559A
0x180415511  mov     rcx, [rsp+0F8h+TokenHandle]; TokenHandle
0x180415516  xor     ebx, ebx
0x180415518  mov     dword ptr [rax], 1
0x18041551e  xor     r9d, r9d; BufferLength
0x180415521  mov     [rsp+0F8h+var_C0], 14h
0x18041552a  mov     r8, rdi; NewState
0x18041552d  mov     rax, [rsp+0F8h+var_C0]
0x180415532  xor     edx, edx; DisableAllPrivileges
0x180415534  mov     [rsp+0F8h+ReturnLength], rbx; ReturnLength
0x180415539  mov     [rdi+4], rax
0x18041553d  mov     dword ptr [rdi+0Ch], 2
0x180415544  mov     [rsp+0F8h+PreviousState], rbx; PreviousState
0x180415549  call    cs:__imp_AdjustTokenPrivileges
0x180415550  nop     dword ptr [rax+rax+00h]
0x180415555  test    eax, eax
0x180415557  jnz     short loc_18041558B
0x180415559  call    cs:__imp_GetLastError
0x180415560  nop     dword ptr [rax+rax+00h]
0x180415565  test    eax, eax
0x180415567  jnz     short loc_180415570
0x180415569  mov     ebx, 80004005h
0x18041556e  jmp     short loc_18041558B
0x180415570  call    cs:__imp_GetLastError
0x180415577  nop     dword ptr [rax+rax+00h]
0x18041557c  mov     ebx, eax
0x18041557e  test    eax, eax
0x180415580  jle     short loc_18041558B
0x180415582  movzx   ebx, ax
0x180415585  or      ebx, 80070000h
0x18041558b  mov     rcx, rdi; Block
0x18041558e  call    cs:__imp_free
0x180415595  nop     dword ptr [rax+rax+00h]
0x18041559a  mov     rcx, [rsp+0F8h+TokenHandle]; hObject
0x18041559f  call    cs:__imp_CloseHandle
0x1804155a6  nop     dword ptr [rax+rax+00h]
0x1804155ab  test    ebx, ebx
0x1804155ad  jnz     loc_180415462
0x1804155b3  mov     cs:byte_1807EC10C, 1
0x1804155ba  jmp     loc_180415462
0x1804155bf  xor     eax, eax
0x1804155c1  mov     rcx, [rsp+0F8h+var_18]
0x1804155c9  xor     rcx, rsp; StackCookie
0x1804155cc  call    __security_check_cookie
0x1804155d1  mov     rbx, [rsp+0F8h+arg_0]
0x1804155d9  add     rsp, 0F0h
0x1804155e0  pop     rdi
0x1804155e1  retn
```
