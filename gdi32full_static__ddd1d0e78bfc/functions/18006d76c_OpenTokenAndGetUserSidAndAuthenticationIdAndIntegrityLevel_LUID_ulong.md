# OpenTokenAndGetUserSidAndAuthenticationIdAndIntegrityLevel(_LUID *,ulong *)

- ea: `0x18006d76c`
- end: `0x18006d8f2`
- name: `?OpenTokenAndGetUserSidAndAuthenticationIdAndIntegrityLevel@@YAPEAXPEAU_LUID@@PEAK@Z`
- size: `390`
- prototype: `void *__fastcall(struct _LUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18009affc`

## callees

- `0x18006d76c`
- `0x18007da1c`
- `0x18007f800`
- `0x180080604`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006d7cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006d7cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006d801`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006d801`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d8c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d8c3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18006d8af`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18006d8af`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18006d898`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18006d898`
- `ntdll!NtOpenThreadToken` at `0x18006d7ea`
- `ntdll!NtOpenThreadToken` at `0x18006d7ea`
- `ntdll!NtOpenProcessToken` at `0x18006d816`
- `ntdll!NtOpenProcessToken` at `0x18006d816`
- `ntdll!NtQueryInformationToken` at `0x18006d853`
- `ntdll!NtQueryInformationToken` at `0x18006d888`
- `ntdll!NtQueryInformationToken` at `0x18006d853`
- `ntdll!NtQueryInformationToken` at `0x18006d888`

## pseudocode

```c
void *__fastcall OpenTokenAndGetUserSidAndAuthenticationIdAndIntegrityLevel(struct _LUID *a1, unsigned int *a2)
{
  HANDLE CurrentThread; // rax
  NTSTATUS v5; // eax
  HANDLE CurrentProcess; // rax
  void *UserSid; // rbx
  PUCHAR SidSubAuthorityCount; // rax
  ULONG TokenInformationLength; // [rsp+30h] [rbp-79h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-71h] BYREF
  int TokenInformation; // [rsp+40h] [rbp-69h] BYREF
  __int128 v13; // [rsp+44h] [rbp-65h]
  __int128 v14; // [rsp+54h] [rbp-55h]
  __int128 v15; // [rsp+64h] [rbp-45h]
  int v16; // [rsp+74h] [rbp-35h]
  PSID pSid[12]; // [rsp+80h] [rbp-29h] BYREF

  TokenHandle = 0;
  TokenInformation = 0;
  v16 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  memset_0(pSid, 0, 0x58u);
  TokenInformationLength = 56;
  CurrentThread = GetCurrentThread();
  v5 = NtOpenThreadToken(CurrentThread, 0x20008u, 1u, &TokenHandle);
  if ( v5 < 0 )
  {
    if ( v5 != -1073741700 )
      return 0;
    CurrentProcess = GetCurrentProcess();
    if ( NtOpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) < 0 )
      return 0;
  }
  UserSid = GetUserSid(TokenHandle);
  NtQueryInformationToken(
    TokenHandle,
    TokenStatistics,
    &TokenInformation,
    TokenInformationLength,
    &TokenInformationLength);
  *a1 = *(struct _LUID *)((char *)&v13 + 4);
  TokenInformationLength = 88;
  NtQueryInformationToken(TokenHandle, TokenIntegrityLevel, pSid, 0x58u, &TokenInformationLength);
  SidSubAuthorityCount = GetSidSubAuthorityCount(pSid[0]);
  *a2 = *GetSidSubAuthority(pSid[0], (unsigned __int8)(*SidSubAuthorityCount - 1));
  CloseHandle(TokenHandle);
  return UserSid;
}

```

## disassembly

```asm
0x18006d76c  mov     [rsp-8+arg_10], rbx
0x18006d771  push    rbp
0x18006d772  push    rsi
0x18006d773  push    rdi
0x18006d774  lea     rbp, [rsp-47h]
0x18006d779  sub     rsp, 0F0h
0x18006d780  mov     rax, cs:__security_cookie
0x18006d787  xor     rax, rsp
0x18006d78a  mov     [rbp+57h+var_20], rax
0x18006d78e  xorps   xmm0, xmm0
0x18006d791  mov     [rbp+57h+TokenHandle], 0
0x18006d799  xor     eax, eax
0x18006d79b  mov     [rbp+57h+TokenInformation], 0
0x18006d7a2  mov     rsi, rdx
0x18006d7a5  mov     [rbp+57h+var_8C], eax
0x18006d7a8  mov     rdi, rcx
0x18006d7ab  xor     edx, edx; Val
0x18006d7ad  lea     rcx, [rbp+57h+pSid]; void *
0x18006d7b1  lea     r8d, [rax+58h]; Size
0x18006d7b5  movups  [rbp+57h+var_BC], xmm0
0x18006d7b9  movups  [rbp+57h+var_AC], xmm0
0x18006d7bd  movups  [rbp+57h+var_9C], xmm0
0x18006d7c1  call    memset_0
0x18006d7c6  mov     [rbp+57h+TokenInformationLength], 38h ; '8'
0x18006d7cd  call    cs:__imp_GetCurrentThread
0x18006d7d4  nop     dword ptr [rax+rax+00h]
0x18006d7d9  mov     ebx, 20008h
0x18006d7de  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18006d7e2  mov     rcx, rax; ThreadHandle
0x18006d7e5  mov     edx, ebx; DesiredAccess
0x18006d7e7  mov     r8b, 1; OpenAsSelf
0x18006d7ea  call    cs:__imp_NtOpenThreadToken
0x18006d7f1  nop     dword ptr [rax+rax+00h]
0x18006d7f6  test    eax, eax
0x18006d7f8  jns     short loc_18006D82D
0x18006d7fa  cmp     eax, 0C000007Ch
0x18006d7ff  jnz     short loc_18006D826
0x18006d801  call    cs:__imp_GetCurrentProcess
0x18006d808  nop     dword ptr [rax+rax+00h]
0x18006d80d  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18006d811  mov     edx, ebx; DesiredAccess
0x18006d813  mov     rcx, rax; ProcessHandle
0x18006d816  call    cs:__imp_NtOpenProcessToken
0x18006d81d  nop     dword ptr [rax+rax+00h]
0x18006d822  test    eax, eax
0x18006d824  jns     short loc_18006D82D
0x18006d826  xor     eax, eax
0x18006d828  jmp     loc_18006D8D2
0x18006d82d  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18006d831  call    ?GetUserSid@@YAPEAXPEAX@Z; GetUserSid(void *)
0x18006d836  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18006d83a  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18006d83e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18006d842  mov     rbx, rax
0x18006d845  lea     rax, [rbp+57h+TokenInformationLength]
0x18006d849  mov     edx, 0Ah; TokenInformationClass
0x18006d84e  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x18006d853  call    cs:__imp_NtQueryInformationToken
0x18006d85a  nop     dword ptr [rax+rax+00h]
0x18006d85f  mov     rcx, qword ptr [rbp+57h+var_BC+4]
0x18006d863  lea     rax, [rbp+57h+TokenInformationLength]
0x18006d867  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18006d86d  mov     [rdi], rcx
0x18006d870  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18006d874  lea     r8, [rbp+57h+pSid]; TokenInformation
0x18006d878  mov     [rbp+57h+TokenInformationLength], 58h ; 'X'
0x18006d87f  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x18006d884  lea     edx, [r9-3Fh]; TokenInformationClass
0x18006d888  call    cs:__imp_NtQueryInformationToken
0x18006d88f  nop     dword ptr [rax+rax+00h]
0x18006d894  mov     rcx, [rbp+57h+pSid]; pSid
0x18006d898  call    cs:__imp_GetSidSubAuthorityCount
0x18006d89f  nop     dword ptr [rax+rax+00h]
0x18006d8a4  mov     cl, [rax]
0x18006d8a6  dec     cl
0x18006d8a8  movzx   edx, cl; nSubAuthority
0x18006d8ab  mov     rcx, [rbp+57h+pSid]; pSid
0x18006d8af  call    cs:__imp_GetSidSubAuthority
0x18006d8b6  nop     dword ptr [rax+rax+00h]
0x18006d8bb  mov     ecx, [rax]
0x18006d8bd  mov     [rsi], ecx
0x18006d8bf  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18006d8c3  call    cs:__imp_CloseHandle
0x18006d8ca  nop     dword ptr [rax+rax+00h]
0x18006d8cf  mov     rax, rbx
0x18006d8d2  mov     rcx, [rbp+57h+var_20]
0x18006d8d6  xor     rcx, rsp; StackCookie
0x18006d8d9  call    __security_check_cookie
0x18006d8de  mov     rbx, [rsp+100h+arg_10]
0x18006d8e6  add     rsp, 0F0h
0x18006d8ed  pop     rdi
0x18006d8ee  pop     rsi
0x18006d8ef  pop     rbp
0x18006d8f0  retn
```
