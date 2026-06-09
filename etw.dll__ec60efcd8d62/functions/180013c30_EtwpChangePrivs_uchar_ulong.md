# EtwpChangePrivs(uchar,ulong *)

- ea: `0x180013c30`
- end: `0x180013d88`
- name: `?EtwpChangePrivs@@YAKEPEAK@Z`
- size: `344`
- prototype: `unsigned int __fastcall(unsigned __int8, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180013e28`

## callees

- `0x180001560`
- `0x180001ff0`
- `0x180002014`
- `0x180013c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ca1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ca1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180013c84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180013c84`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180013c97`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180013c97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013d58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013d58`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180013d1c`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180013d1c`

## pseudocode

```c
__int64 __fastcall EtwpChangePrivs(char a1, unsigned int *a2)
{
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  char *v6; // rax
  struct _TOKEN_PRIVILEGES *v7; // rdi
  int v8; // eax
  DWORD Attributes; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-848h] BYREF
  void *TokenHandle[3]; // [rsp+38h] [rbp-840h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+50h] [rbp-828h] BYREF

  TokenHandle[0] = (void *)-1LL;
  ReturnLength = 0;
  if ( a1 || *a2 != 2 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x28u, TokenHandle) )
    {
      LastError = 8;
      TokenHandle[1] = (void *)8;
      v6 = (char *)operator new(0x1Cu, (const struct std::nothrow_t *)&std::nothrow);
      v7 = (struct _TOKEN_PRIVILEGES *)v6;
      if ( v6 )
      {
        *(_QWORD *)(v6 + 12) = 0;
        *(_QWORD *)(v6 + 20) = 0;
        *(_DWORD *)v6 = 1;
        *(_QWORD *)(v6 + 4) = 8;
        v8 = 2;
        if ( !a1 )
          v8 = *a2;
        v7->Privileges[0].Attributes = v8;
        if ( AdjustTokenPrivileges(TokenHandle[0], 0, v7, 0x800u, &PreviousState, &ReturnLength) )
        {
          LastError = 0;
          if ( a1 )
          {
            Attributes = PreviousState.Privileges[0].Attributes;
            if ( !PreviousState.PrivilegeCount )
              Attributes = 2;
            *a2 = Attributes;
          }
        }
        else
        {
          LastError = GetLastError();
        }
        operator delete(v7);
      }
    }
    else
    {
      LastError = GetLastError();
    }
    if ( TokenHandle[0] != (void *)-1LL )
      CloseHandle(TokenHandle[0]);
  }
  else
  {
    return 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x180013c30  mov     [rsp+arg_0], rbx
0x180013c35  mov     [rsp+arg_10], rbp
0x180013c3a  push    rsi
0x180013c3b  push    rdi
0x180013c3c  push    r15
0x180013c3e  sub     rsp, 860h
0x180013c45  mov     rax, cs:__security_cookie
0x180013c4c  xor     rax, rsp
0x180013c4f  mov     [rsp+878h+var_28], rax
0x180013c57  mov     [rsp+878h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180013c60  mov     rsi, rdx
0x180013c63  mov     [rsp+878h+var_848], 0
0x180013c6b  mov     bpl, cl
0x180013c6e  mov     r15d, 2
0x180013c74  test    cl, cl
0x180013c76  jnz     short loc_180013C84
0x180013c78  cmp     [rdx], r15d
0x180013c7b  jnz     short loc_180013C84
0x180013c7d  xor     ebx, ebx
0x180013c7f  jmp     loc_180013D5E
0x180013c84  call    cs:__imp_GetCurrentProcess
0x180013c8a  lea     r8, [rsp+878h+TokenHandle]; TokenHandle
0x180013c8f  mov     edx, 28h ; '('; DesiredAccess
0x180013c94  mov     rcx, rax; ProcessHandle
0x180013c97  call    cs:__imp_OpenProcessToken
0x180013c9d  test    eax, eax
0x180013c9f  jnz     short loc_180013CAE
0x180013ca1  call    cs:__imp_GetLastError
0x180013ca7  mov     ebx, eax
0x180013ca9  jmp     loc_180013D4D
0x180013cae  mov     ebx, 8
0x180013cb3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013cba  mov     [rsp+878h+var_838], rbx
0x180013cbf  lea     ecx, [rbx+14h]; unsigned __int64
0x180013cc2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180013cc7  mov     rdi, rax
0x180013cca  test    rax, rax
0x180013ccd  jz      short loc_180013D4D
0x180013ccf  mov     qword ptr [rax+0Ch], 0
0x180013cd7  mov     ecx, ebx
0x180013cd9  mov     qword ptr [rax+14h], 0
0x180013ce1  mov     dword ptr [rax], 1
0x180013ce7  mov     [rax+4], rbx
0x180013ceb  mov     eax, r15d
0x180013cee  test    bpl, bpl
0x180013cf1  jnz     short loc_180013CF5
0x180013cf3  mov     eax, [rsi]
0x180013cf5  mov     [rdi+0Ch], eax
0x180013cf8  mov     r9d, 800h; BufferLength
0x180013cfe  mov     rcx, [rsp+878h+TokenHandle]; TokenHandle
0x180013d03  lea     rax, [rsp+878h+var_848]
0x180013d08  mov     [rsp+878h+ReturnLength], rax; ReturnLength
0x180013d0d  mov     r8, rdi; NewState
0x180013d10  lea     rax, [rsp+878h+var_828]
0x180013d15  xor     edx, edx; DisableAllPrivileges
0x180013d17  mov     [rsp+878h+PreviousState], rax; PreviousState
0x180013d1c  call    cs:__imp_AdjustTokenPrivileges
0x180013d22  test    eax, eax
0x180013d24  jnz     short loc_180013D30
0x180013d26  call    cs:__imp_GetLastError
0x180013d2c  mov     ebx, eax
0x180013d2e  jmp     short loc_180013D45
0x180013d30  xor     ebx, ebx
0x180013d32  test    bpl, bpl
0x180013d35  jz      short loc_180013D45
0x180013d37  cmp     [rsp+878h+var_828.PrivilegeCount], ebx
0x180013d3b  mov     eax, [rsp+878h+var_828.Privileges.Attributes]
0x180013d3f  cmovz   eax, r15d
0x180013d43  mov     [rsi], eax
0x180013d45  mov     rcx, rdi; Block
0x180013d48  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013d4d  mov     rcx, [rsp+878h+TokenHandle]; hObject
0x180013d52  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180013d56  jz      short loc_180013D5E
0x180013d58  call    cs:__imp_CloseHandle
0x180013d5e  mov     eax, ebx
0x180013d60  mov     rcx, [rsp+878h+var_28]
0x180013d68  xor     rcx, rsp; StackCookie
0x180013d6b  call    __security_check_cookie
0x180013d70  lea     r11, [rsp+878h+var_18]
0x180013d78  mov     rbx, [r11+20h]
0x180013d7c  mov     rbp, [r11+30h]
0x180013d80  mov     rsp, r11
0x180013d83  pop     r15
0x180013d85  pop     rdi
0x180013d86  pop     rsi
0x180013d87  retn
```
