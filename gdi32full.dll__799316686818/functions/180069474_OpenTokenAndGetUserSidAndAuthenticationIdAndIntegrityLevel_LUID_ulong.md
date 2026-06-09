# OpenTokenAndGetUserSidAndAuthenticationIdAndIntegrityLevel(_LUID *,ulong *)

- ea: `0x180069474`
- end: `0x1800695c3`
- name: `?OpenTokenAndGetUserSidAndAuthenticationIdAndIntegrityLevel@@YAPEAXPEAU_LUID@@PEAK@Z`
- size: `335`
- prototype: `void *__fastcall(struct _LUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180095128`

## callees

- `0x180069474`
- `0x180078ebc`
- `0x18007ac50`
- `0x18007ba24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800694d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800694d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800694fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800694fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006959b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006959b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18006958d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18006958d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18006957c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18006957c`
- `ntdll!NtOpenThreadToken` at `0x1800694ec`
- `ntdll!NtOpenThreadToken` at `0x1800694ec`
- `ntdll!NtOpenProcessToken` at `0x18006950c`
- `ntdll!NtOpenProcessToken` at `0x18006950c`
- `ntdll!NtQueryInformationToken` at `0x180069543`
- `ntdll!NtQueryInformationToken` at `0x180069572`
- `ntdll!NtQueryInformationToken` at `0x180069543`
- `ntdll!NtQueryInformationToken` at `0x180069572`

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
0x180069474  mov     [rsp-8+arg_10], rbx
0x180069479  push    rbp
0x18006947a  push    rsi
0x18006947b  push    rdi
0x18006947c  lea     rbp, [rsp-47h]
0x180069481  sub     rsp, 0F0h
0x180069488  mov     rax, cs:__security_cookie
0x18006948f  xor     rax, rsp
0x180069492  mov     [rbp+57h+var_20], rax
0x180069496  xorps   xmm0, xmm0
0x180069499  mov     [rbp+57h+TokenHandle], 0
0x1800694a1  xor     eax, eax
0x1800694a3  mov     [rbp+57h+TokenInformation], 0
0x1800694aa  mov     rsi, rdx
0x1800694ad  mov     [rbp+57h+var_8C], eax
0x1800694b0  mov     rdi, rcx
0x1800694b3  xor     edx, edx; Val
0x1800694b5  lea     rcx, [rbp+57h+pSid]; void *
0x1800694b9  lea     r8d, [rax+58h]; Size
0x1800694bd  movups  [rbp+57h+var_BC], xmm0
0x1800694c1  movups  [rbp+57h+var_AC], xmm0
0x1800694c5  movups  [rbp+57h+var_9C], xmm0
0x1800694c9  call    memset_0
0x1800694ce  mov     [rbp+57h+TokenInformationLength], 38h ; '8'
0x1800694d5  call    cs:__imp_GetCurrentThread
0x1800694db  mov     ebx, 20008h
0x1800694e0  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800694e4  mov     rcx, rax; ThreadHandle
0x1800694e7  mov     edx, ebx; DesiredAccess
0x1800694e9  mov     r8b, 1; OpenAsSelf
0x1800694ec  call    cs:__imp_NtOpenThreadToken
0x1800694f2  test    eax, eax
0x1800694f4  jns     short loc_18006951D
0x1800694f6  cmp     eax, 0C000007Ch
0x1800694fb  jnz     short loc_180069516
0x1800694fd  call    cs:__imp_GetCurrentProcess
0x180069503  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180069507  mov     edx, ebx; DesiredAccess
0x180069509  mov     rcx, rax; ProcessHandle
0x18006950c  call    cs:__imp_NtOpenProcessToken
0x180069512  test    eax, eax
0x180069514  jns     short loc_18006951D
0x180069516  xor     eax, eax
0x180069518  jmp     loc_1800695A4
0x18006951d  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180069521  call    ?GetUserSid@@YAPEAXPEAX@Z; GetUserSid(void *)
0x180069526  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18006952a  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18006952e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180069532  mov     rbx, rax
0x180069535  lea     rax, [rbp+57h+TokenInformationLength]
0x180069539  mov     edx, 0Ah; TokenInformationClass
0x18006953e  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x180069543  call    cs:__imp_NtQueryInformationToken
0x180069549  mov     rcx, qword ptr [rbp+57h+var_BC+4]
0x18006954d  lea     rax, [rbp+57h+TokenInformationLength]
0x180069551  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180069557  mov     [rdi], rcx
0x18006955a  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18006955e  lea     r8, [rbp+57h+pSid]; TokenInformation
0x180069562  mov     [rbp+57h+TokenInformationLength], 58h ; 'X'
0x180069569  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x18006956e  lea     edx, [r9-3Fh]; TokenInformationClass
0x180069572  call    cs:__imp_NtQueryInformationToken
0x180069578  mov     rcx, [rbp+57h+pSid]; pSid
0x18006957c  call    cs:__imp_GetSidSubAuthorityCount
0x180069582  mov     cl, [rax]
0x180069584  dec     cl
0x180069586  movzx   edx, cl; nSubAuthority
0x180069589  mov     rcx, [rbp+57h+pSid]; pSid
0x18006958d  call    cs:__imp_GetSidSubAuthority
0x180069593  mov     ecx, [rax]
0x180069595  mov     [rsi], ecx
0x180069597  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18006959b  call    cs:__imp_CloseHandle
0x1800695a1  mov     rax, rbx
0x1800695a4  mov     rcx, [rbp+57h+var_20]
0x1800695a8  xor     rcx, rsp; StackCookie
0x1800695ab  call    __security_check_cookie
0x1800695b0  mov     rbx, [rsp+100h+arg_10]
0x1800695b8  add     rsp, 0F0h
0x1800695bf  pop     rdi
0x1800695c0  pop     rsi
0x1800695c1  pop     rbp
0x1800695c2  retn
```
