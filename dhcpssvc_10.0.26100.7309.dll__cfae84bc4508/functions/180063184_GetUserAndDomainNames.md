# GetUserAndDomainNames

- ea: `0x180063184`
- end: `0x180063361`
- name: `GetUserAndDomainNames`
- size: `477`
- prototype: `__int64 __fastcall(LPWSTR Name, LPDWORD cchName, LPWSTR ReferencedDomainName, LPDWORD cchReferencedDomainName)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18006308c`

## callees

- `0x180063184`

## import_xrefs

- `ADVAPI32!LookupAccountSidW` at `0x1800632f7`
- `ADVAPI32!LookupAccountSidW` at `0x1800632f7`
- `ADVAPI32!GetTokenInformation` at `0x18006326e`
- `ADVAPI32!GetTokenInformation` at `0x1800632c9`
- `ADVAPI32!GetTokenInformation` at `0x18006326e`
- `ADVAPI32!GetTokenInformation` at `0x1800632c9`
- `ADVAPI32!OpenThreadToken` at `0x1800631e0`
- `ADVAPI32!OpenThreadToken` at `0x18006321d`
- `ADVAPI32!OpenThreadToken` at `0x1800631e0`
- `ADVAPI32!OpenThreadToken` at `0x18006321d`
- `RPCRT4!RpcImpersonateClient` at `0x1800631b9`
- `RPCRT4!RpcImpersonateClient` at `0x1800631b9`
- `RPCRT4!RpcRevertToSelf` at `0x180063245`
- `RPCRT4!RpcRevertToSelf` at `0x180063338`
- `RPCRT4!RpcRevertToSelf` at `0x180063245`
- `RPCRT4!RpcRevertToSelf` at `0x180063338`
- `KERNEL32!GetCurrentThread` at `0x1800631c7`
- `KERNEL32!GetCurrentThread` at `0x180063204`
- `KERNEL32!GetCurrentThread` at `0x1800631c7`
- `KERNEL32!GetCurrentThread` at `0x180063204`
- `KERNEL32!LocalAlloc` at `0x18006329c`
- `KERNEL32!LocalAlloc` at `0x18006329c`
- `KERNEL32!GetLastError` at `0x1800631f3`
- `KERNEL32!GetLastError` at `0x18006322d`
- `KERNEL32!GetLastError` at `0x180063281`
- `KERNEL32!GetLastError` at `0x180063307`
- `KERNEL32!GetLastError` at `0x1800631f3`
- `KERNEL32!GetLastError` at `0x18006322d`
- `KERNEL32!GetLastError` at `0x180063281`
- `KERNEL32!GetLastError` at `0x180063307`
- `KERNEL32!CloseHandle` at `0x180063328`
- `KERNEL32!CloseHandle` at `0x180063328`
- `KERNEL32!LocalFree` at `0x180063318`
- `KERNEL32!LocalFree` at `0x180063318`

## pseudocode

```c
DWORD __fastcall GetUserAndDomainNames(
        LPWSTR Name,
        LPDWORD cchName,
        LPWSTR ReferencedDomainName,
        LPDWORD cchReferencedDomainName)
{
  DWORD LastError; // ebx
  RPC_STATUS v9; // esi
  HANDLE CurrentThread; // rax
  DWORD result; // eax
  HANDLE v12; // rax
  PSID *v13; // rdi
  void *TokenHandle[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+90h] [rbp+40h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+A0h] [rbp+50h] BYREF

  LastError = 0;
  *ReferencedDomainName = 0;
  *Name = 0;
  TokenHandle[0] = 0;
  peUse = 0;
  v9 = RpcImpersonateClient(0);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, TokenHandle) )
    goto LABEL_8;
  result = GetLastError();
  if ( result == 5 )
  {
    v12 = GetCurrentThread();
    if ( OpenThreadToken(v12, 8u, 1, TokenHandle) )
      goto LABEL_8;
    result = GetLastError();
  }
  if ( result )
  {
    if ( !v9 )
      return RpcRevertToSelf();
    return result;
  }
LABEL_8:
  TokenInformationLength = 0;
  GetTokenInformation(TokenHandle[0], TokenUser, 0, 0, &TokenInformationLength);
  if ( TokenInformationLength
    && (v13 = (PSID *)LocalAlloc(0x40u, TokenInformationLength)) != 0
    && GetTokenInformation(TokenHandle[0], TokenUser, v13, TokenInformationLength, &TokenInformationLength) )
  {
    if ( !LookupAccountSidW(0, *v13, Name, cchName, ReferencedDomainName, cchReferencedDomainName, &peUse) )
      LastError = GetLastError();
    LocalFree(v13);
  }
  else
  {
    LastError = GetLastError();
  }
  CloseHandle(TokenHandle[0]);
  if ( !v9 )
    return RpcRevertToSelf();
  return LastError;
}

```

## disassembly

```asm
0x180063184  mov     [rsp-38h+arg_8], rbx
0x180063189  push    rbp
0x18006318a  push    rsi
0x18006318b  push    rdi
0x18006318c  push    r12
0x18006318e  push    r13
0x180063190  push    r14
0x180063192  push    r15
0x180063194  mov     rbp, rsp
0x180063197  sub     rsp, 50h
0x18006319b  xor     ebx, ebx
0x18006319d  mov     r15, rcx
0x1800631a0  mov     [r8], bx
0x1800631a4  mov     r12, r9
0x1800631a7  mov     [rcx], bx
0x1800631aa  mov     r14, r8
0x1800631ad  xor     ecx, ecx; BindingHandle
0x1800631af  mov     [rbp+TokenHandle], rbx
0x1800631b3  mov     r13, rdx
0x1800631b6  mov     [rbp+arg_10], ebx
0x1800631b9  call    cs:__imp_RpcImpersonateClient
0x1800631c0  nop     dword ptr [rax+rax+00h]
0x1800631c5  mov     esi, eax
0x1800631c7  call    cs:__imp_GetCurrentThread
0x1800631ce  nop     dword ptr [rax+rax+00h]
0x1800631d3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800631d7  xor     r8d, r8d; OpenAsSelf
0x1800631da  mov     rcx, rax; ThreadHandle
0x1800631dd  lea     edx, [rbx+8]; DesiredAccess
0x1800631e0  call    cs:__imp_OpenThreadToken
0x1800631e7  nop     dword ptr [rax+rax+00h]
0x1800631ec  lea     edi, [rbx+1]
0x1800631ef  test    eax, eax
0x1800631f1  jnz     short loc_180063256
0x1800631f3  call    cs:__imp_GetLastError
0x1800631fa  nop     dword ptr [rax+rax+00h]
0x1800631ff  cmp     eax, 5
0x180063202  jnz     short loc_180063239
0x180063204  call    cs:__imp_GetCurrentThread
0x18006320b  nop     dword ptr [rax+rax+00h]
0x180063210  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180063214  mov     r8d, edi; OpenAsSelf
0x180063217  mov     rcx, rax; ThreadHandle
0x18006321a  lea     edx, [rbx+8]; DesiredAccess
0x18006321d  call    cs:__imp_OpenThreadToken
0x180063224  nop     dword ptr [rax+rax+00h]
0x180063229  test    eax, eax
0x18006322b  jnz     short loc_180063256
0x18006322d  call    cs:__imp_GetLastError
0x180063234  nop     dword ptr [rax+rax+00h]
0x180063239  test    eax, eax
0x18006323b  jz      short loc_180063256
0x18006323d  test    esi, esi
0x18006323f  jnz     loc_180063348
0x180063245  call    cs:__imp_RpcRevertToSelf
0x18006324c  nop     dword ptr [rax+rax+00h]
0x180063251  jmp     loc_180063348
0x180063256  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18006325a  lea     rax, [rbp+TokenInformationLength]
0x18006325e  xor     r9d, r9d; TokenInformationLength
0x180063261  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180063266  xor     r8d, r8d; TokenInformation
0x180063269  mov     [rbp+TokenInformationLength], ebx
0x18006326c  mov     edx, edi; TokenInformationClass
0x18006326e  call    cs:__imp_GetTokenInformation
0x180063275  nop     dword ptr [rax+rax+00h]
0x18006327a  mov     eax, [rbp+TokenInformationLength]
0x18006327d  test    eax, eax
0x18006327f  jnz     short loc_180063294
0x180063281  call    cs:__imp_GetLastError
0x180063288  nop     dword ptr [rax+rax+00h]
0x18006328d  mov     ebx, eax
0x18006328f  jmp     loc_180063324
0x180063294  mov     rdx, rax; uBytes
0x180063297  mov     ecx, 40h ; '@'; uFlags
0x18006329c  call    cs:__imp_LocalAlloc
0x1800632a3  nop     dword ptr [rax+rax+00h]
0x1800632a8  mov     rdi, rax
0x1800632ab  test    rax, rax
0x1800632ae  jz      short loc_180063281
0x1800632b0  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800632b4  lea     rax, [rbp+TokenInformationLength]
0x1800632b8  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800632bc  mov     r8, rdi; TokenInformation
0x1800632bf  mov     edx, 1; TokenInformationClass
0x1800632c4  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1800632c9  call    cs:__imp_GetTokenInformation
0x1800632d0  nop     dword ptr [rax+rax+00h]
0x1800632d5  test    eax, eax
0x1800632d7  jz      short loc_180063281
0x1800632d9  mov     rdx, [rdi]; Sid
0x1800632dc  lea     rax, [rbp+arg_10]
0x1800632e0  mov     [rsp+50h+peUse], rax; peUse
0x1800632e5  mov     r9, r13; cchName
0x1800632e8  mov     [rsp+50h+cchReferencedDomainName], r12; cchReferencedDomainName
0x1800632ed  mov     r8, r15; Name
0x1800632f0  xor     ecx, ecx; lpSystemName
0x1800632f2  mov     [rsp+50h+ReturnLength], r14; ReferencedDomainName
0x1800632f7  call    cs:__imp_LookupAccountSidW
0x1800632fe  nop     dword ptr [rax+rax+00h]
0x180063303  test    eax, eax
0x180063305  jnz     short loc_180063315
0x180063307  call    cs:__imp_GetLastError
0x18006330e  nop     dword ptr [rax+rax+00h]
0x180063313  mov     ebx, eax
0x180063315  mov     rcx, rdi; hMem
0x180063318  call    cs:__imp_LocalFree
0x18006331f  nop     dword ptr [rax+rax+00h]
0x180063324  mov     rcx, [rbp+TokenHandle]; hObject
0x180063328  call    cs:__imp_CloseHandle
0x18006332f  nop     dword ptr [rax+rax+00h]
0x180063334  test    esi, esi
0x180063336  jnz     short loc_180063346
0x180063338  call    cs:__imp_RpcRevertToSelf
0x18006333f  nop     dword ptr [rax+rax+00h]
0x180063344  mov     ebx, eax
0x180063346  mov     eax, ebx
0x180063348  mov     rbx, [rsp+50h+arg_8]
0x180063350  add     rsp, 50h
0x180063354  pop     r15
0x180063356  pop     r14
0x180063358  pop     r13
0x18006335a  pop     r12
0x18006335c  pop     rdi
0x18006335d  pop     rsi
0x18006335e  pop     rbp
0x18006335f  retn
```
