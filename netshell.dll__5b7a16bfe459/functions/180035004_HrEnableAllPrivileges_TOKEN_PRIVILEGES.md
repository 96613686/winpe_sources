# HrEnableAllPrivileges(_TOKEN_PRIVILEGES * *)

- ea: `0x180035004`
- end: `0x180035148`
- name: `?HrEnableAllPrivileges@@YAJPEAPEAU_TOKEN_PRIVILEGES@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(struct _TOKEN_PRIVILEGES **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003fedc`

## callees

- `0x180002010`
- `0x180009140`
- `0x180034ba0`
- `0x180035004`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003504f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003504f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180035060`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180035060`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180035043`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180035043`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003502b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003502b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003506f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003506f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035122`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035122`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800350ff`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800350ff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800350b1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800350b1`

## pseudocode

```c
__int64 __fastcall HrEnableAllPrivileges(struct _TOKEN_PRIVILEGES **a1)
{
  HANDLE CurrentThread; // rax
  BOOL TokenInformation; // edi
  HANDLE CurrentProcess; // rax
  unsigned int v5; // esi
  struct _TOKEN_PRIVILEGES *v6; // rbx
  DWORD v7; // ecx
  __int64 v8; // rax
  struct _TOKEN_PRIVILEGES *v9; // rax
  DWORD v10; // r9d
  void *v11; // rcx
  DWORD TokenInformationLength; // [rsp+58h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF

  TokenHandle = 0;
  TokenInformationLength = 4096;
  CurrentThread = GetCurrentThread();
  TokenInformation = OpenThreadToken(CurrentThread, 0x28u, 1, &TokenHandle);
  if ( !TokenInformation )
  {
    if ( GetLastError() != 1008 )
      return (unsigned int)HrFromLastWin32Error();
    CurrentProcess = GetCurrentProcess();
    TokenInformation = OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle);
    if ( !TokenInformation )
      return (unsigned int)HrFromLastWin32Error();
  }
  v5 = -2147024882;
  v6 = (struct _TOKEN_PRIVILEGES *)MemAlloc(TokenInformationLength);
  if ( v6 )
  {
    v5 = 0;
    TokenInformation = GetTokenInformation(
                         TokenHandle,
                         TokenPrivileges,
                         v6,
                         TokenInformationLength,
                         &TokenInformationLength);
    if ( TokenInformation )
    {
      if ( v6->PrivilegeCount )
      {
        v7 = 0;
        do
        {
          v8 = v7++;
          v6->Privileges[v8].Attributes = 2;
        }
        while ( v7 < v6->PrivilegeCount );
      }
      v9 = (struct _TOKEN_PRIVILEGES *)MemAlloc(TokenInformationLength);
      v10 = TokenInformationLength;
      v11 = TokenHandle;
      *a1 = v9;
      TokenInformation = AdjustTokenPrivileges(v11, 0, v6, v10, v9, &TokenInformationLength);
      if ( !TokenInformation )
      {
        MemFree(*a1);
        *a1 = 0;
      }
    }
    MemFree(v6);
  }
  CloseHandle(TokenHandle);
  if ( !TokenInformation )
    return (unsigned int)HrFromLastWin32Error();
  return v5;
}

```

## disassembly

```asm
0x180035004  mov     [rsp-18h+arg_0], rbx
0x180035009  mov     [rsp-18h+arg_18], rsi
0x18003500e  push    rbp
0x18003500f  push    rdi
0x180035010  push    r14
0x180035012  mov     rbp, rsp
0x180035015  sub     rsp, 30h
0x180035019  mov     r14, rcx
0x18003501c  mov     [rbp+TokenHandle], 0
0x180035024  mov     [rbp+TokenInformationLength], 1000h
0x18003502b  call    cs:__imp_GetCurrentThread
0x180035031  mov     ebx, 28h ; '('
0x180035036  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18003503a  mov     rcx, rax; ThreadHandle
0x18003503d  mov     edx, ebx; DesiredAccess
0x18003503f  lea     r8d, [rbx-27h]; OpenAsSelf
0x180035043  call    cs:__imp_OpenThreadToken
0x180035049  mov     edi, eax
0x18003504b  test    eax, eax
0x18003504d  jnz     short loc_18003507F
0x18003504f  call    cs:__imp_GetLastError
0x180035055  cmp     eax, 3F0h
0x18003505a  jnz     loc_18003512C
0x180035060  call    cs:__imp_GetCurrentProcess
0x180035066  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18003506a  mov     edx, ebx; DesiredAccess
0x18003506c  mov     rcx, rax; ProcessHandle
0x18003506f  call    cs:__imp_OpenProcessToken
0x180035075  mov     edi, eax
0x180035077  test    eax, eax
0x180035079  jz      loc_18003512C
0x18003507f  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x180035082  mov     esi, 8007000Eh
0x180035087  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18003508c  mov     rbx, rax
0x18003508f  test    rax, rax
0x180035092  jz      loc_18003511E
0x180035098  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18003509c  lea     rax, [rbp+TokenInformationLength]
0x1800350a0  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800350a4  xor     esi, esi
0x1800350a6  mov     r8, rbx; TokenInformation
0x1800350a9  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800350ae  lea     edx, [rsi+3]; TokenInformationClass
0x1800350b1  call    cs:__imp_GetTokenInformation
0x1800350b7  mov     edi, eax
0x1800350b9  test    eax, eax
0x1800350bb  jz      short loc_180035116
0x1800350bd  cmp     [rbx], esi
0x1800350bf  jbe     short loc_1800350D9
0x1800350c1  xor     ecx, ecx
0x1800350c3  mov     eax, ecx
0x1800350c5  inc     ecx
0x1800350c7  inc     rax
0x1800350ca  lea     rax, [rax+rax*2]
0x1800350ce  mov     dword ptr [rbx+rax*4], 2
0x1800350d5  cmp     ecx, [rbx]
0x1800350d7  jb      short loc_1800350C3
0x1800350d9  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x1800350dc  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x1800350e1  mov     r9d, [rbp+TokenInformationLength]; BufferLength
0x1800350e5  lea     rcx, [rbp+TokenInformationLength]
0x1800350e9  mov     [rsp+30h+var_8], rcx; ReturnLength
0x1800350ee  mov     r8, rbx; NewState
0x1800350f1  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800350f5  xor     edx, edx; DisableAllPrivileges
0x1800350f7  mov     [r14], rax
0x1800350fa  mov     [rsp+30h+ReturnLength], rax; PreviousState
0x1800350ff  call    cs:__imp_AdjustTokenPrivileges
0x180035105  mov     edi, eax
0x180035107  test    eax, eax
0x180035109  jnz     short loc_180035116
0x18003510b  mov     rcx, [r14]; lpMem
0x18003510e  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180035113  mov     [r14], rsi
0x180035116  mov     rcx, rbx; lpMem
0x180035119  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18003511e  mov     rcx, [rbp+TokenHandle]; hObject
0x180035122  call    cs:__imp_CloseHandle
0x180035128  test    edi, edi
0x18003512a  jnz     short loc_180035133
0x18003512c  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180035131  mov     esi, eax
0x180035133  mov     rbx, [rsp+30h+arg_0]
0x180035138  mov     eax, esi
0x18003513a  mov     rsi, [rsp+30h+arg_18]
0x18003513f  add     rsp, 30h
0x180035143  pop     r14
0x180035145  pop     rdi
0x180035146  pop     rbp
0x180035147  retn
```
