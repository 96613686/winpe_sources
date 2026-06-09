# AccessImpersonateCheckRpcClientEx

- ea: `0x140059888`
- end: `0x1400599bd`
- name: `AccessImpersonateCheckRpcClientEx`
- size: `309`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, PGENERIC_MAPPING GenericMapping, DWORD DesiredAccess)`
- caller_count: `12`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003370`
- `0x140003620`
- `0x140003910`
- `0x140003f60`
- `0x1400048b0`
- `0x140004b10`
- `0x140005590`
- `0x140005800`
- `0x14000c214`
- `0x140045dec`
- `0x140059558`
- `0x140059e24`

## callees

- `0x140059888`
- `0x14005ce70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059960`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059960`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x14005994f`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x14005994f`
- `RPCRT4!RpcRevertToSelf` at `0x14005996e`
- `RPCRT4!RpcRevertToSelf` at `0x14005996e`
- `RPCRT4!RpcImpersonateClient` at `0x1400598cc`
- `RPCRT4!RpcImpersonateClient` at `0x1400598cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140059984`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140059984`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400598ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400598ec`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140059909`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140059909`

## pseudocode

```c
__int64 __fastcall AccessImpersonateCheckRpcClientEx(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        PGENERIC_MAPPING GenericMapping,
        DWORD DesiredAccess)
{
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  WINBOOL AccessStatus; // [rsp+40h] [rbp-C0h] BYREF
  DWORD GrantedAccess; // [rsp+44h] [rbp-BCh] BYREF
  DWORD PrivilegeSetLength; // [rsp+48h] [rbp-B8h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+60h] [rbp-A0h] BYREF

  AccessStatus = 0;
  GrantedAccess = 0;
  TokenHandle = 0;
  LastError = 0;
  if ( RpcImpersonateClient(0) )
    return 5;
  PrivilegeSetLength = 500;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle)
    && !AccessCheck(
          pSecurityDescriptor,
          TokenHandle,
          DesiredAccess,
          GenericMapping,
          &PrivilegeSet,
          &PrivilegeSetLength,
          &GrantedAccess,
          &AccessStatus) )
  {
    LastError = GetLastError();
  }
  RpcRevertToSelf();
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( !AccessStatus )
    return 5;
  return LastError;
}

```

## disassembly

```asm
0x140059888  push    rbp
0x14005988a  push    rbx
0x14005988b  push    rsi
0x14005988c  push    rdi
0x14005988d  push    r14
0x14005988f  lea     rbp, [rsp-170h]
0x140059897  sub     rsp, 270h
0x14005989e  mov     rax, cs:__security_cookie
0x1400598a5  xor     rax, rsp
0x1400598a8  mov     [rbp+190h+var_30], rax
0x1400598af  and     [rsp+290h+var_250], 0
0x1400598b4  mov     rdi, rcx
0x1400598b7  and     [rsp+290h+var_24C], 0
0x1400598bc  xor     ecx, ecx; BindingHandle
0x1400598be  and     [rsp+290h+TokenHandle], 0
0x1400598c4  mov     r14d, r8d
0x1400598c7  mov     rsi, rdx
0x1400598ca  xor     ebx, ebx
0x1400598cc  call    cs:__imp_RpcImpersonateClient
0x1400598d3  nop     dword ptr [rax+rax+00h]
0x1400598d8  test    eax, eax
0x1400598da  jz      short loc_1400598E4
0x1400598dc  lea     eax, [rbx+5]
0x1400598df  jmp     loc_14005999F
0x1400598e4  mov     [rsp+290h+var_248], 1F4h
0x1400598ec  call    cs:__imp_GetCurrentThread
0x1400598f3  nop     dword ptr [rax+rax+00h]
0x1400598f8  mov     edx, 0Ch; DesiredAccess
0x1400598fd  lea     r9, [rsp+290h+TokenHandle]; TokenHandle
0x140059902  mov     rcx, rax; ThreadHandle
0x140059905  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x140059909  call    cs:__imp_OpenThreadToken
0x140059910  nop     dword ptr [rax+rax+00h]
0x140059915  test    eax, eax
0x140059917  jz      short loc_14005996E
0x140059919  mov     rdx, [rsp+290h+TokenHandle]; ClientToken
0x14005991e  lea     rax, [rsp+290h+var_250]
0x140059923  mov     [rsp+290h+AccessStatus], rax; AccessStatus
0x140059928  mov     r9, rsi; GenericMapping
0x14005992b  lea     rax, [rsp+290h+var_24C]
0x140059930  mov     r8d, r14d; DesiredAccess
0x140059933  mov     [rsp+290h+GrantedAccess], rax; GrantedAccess
0x140059938  mov     rcx, rdi; pSecurityDescriptor
0x14005993b  lea     rax, [rsp+290h+var_248]
0x140059940  mov     [rsp+290h+PrivilegeSetLength], rax; PrivilegeSetLength
0x140059945  lea     rax, [rsp+290h+var_230]
0x14005994a  mov     [rsp+290h+PrivilegeSet], rax; PrivilegeSet
0x14005994f  call    cs:__imp_AccessCheck
0x140059956  nop     dword ptr [rax+rax+00h]
0x14005995b  cmp     eax, 1
0x14005995e  jz      short loc_14005996E
0x140059960  call    cs:__imp_GetLastError
0x140059967  nop     dword ptr [rax+rax+00h]
0x14005996c  mov     ebx, eax
0x14005996e  call    cs:__imp_RpcRevertToSelf
0x140059975  nop     dword ptr [rax+rax+00h]
0x14005997a  mov     rcx, [rsp+290h+TokenHandle]; hObject
0x14005997f  test    rcx, rcx
0x140059982  jz      short loc_140059990
0x140059984  call    cs:__imp_CloseHandle
0x14005998b  nop     dword ptr [rax+rax+00h]
0x140059990  cmp     [rsp+290h+var_250], 0
0x140059995  mov     eax, 5
0x14005999a  cmovz   ebx, eax
0x14005999d  mov     eax, ebx
0x14005999f  mov     rcx, [rbp+190h+var_30]
0x1400599a6  xor     rcx, rsp; StackCookie
0x1400599a9  call    __security_check_cookie
0x1400599ae  add     rsp, 270h
0x1400599b5  pop     r14
0x1400599b7  pop     rdi
0x1400599b8  pop     rsi
0x1400599b9  pop     rbx
0x1400599ba  pop     rbp
0x1400599bb  retn
```
