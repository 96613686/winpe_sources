# GetUserAndDomainNames

- ea: `0x180062f00`
- end: `0x1800630dd`
- name: `GetUserAndDomainNames`
- size: `477`
- prototype: `__int64 __fastcall(LPWSTR Name, LPDWORD cchName, LPWSTR ReferencedDomainName, LPDWORD cchReferencedDomainName)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180062e10`

## callees

- `0x180062f00`

## import_xrefs

- `ADVAPI32!LookupAccountSidW` at `0x180063073`
- `ADVAPI32!LookupAccountSidW` at `0x180063073`
- `ADVAPI32!GetTokenInformation` at `0x180062fea`
- `ADVAPI32!GetTokenInformation` at `0x180063045`
- `ADVAPI32!GetTokenInformation` at `0x180062fea`
- `ADVAPI32!GetTokenInformation` at `0x180063045`
- `ADVAPI32!OpenThreadToken` at `0x180062f5c`
- `ADVAPI32!OpenThreadToken` at `0x180062f99`
- `ADVAPI32!OpenThreadToken` at `0x180062f5c`
- `ADVAPI32!OpenThreadToken` at `0x180062f99`
- `RPCRT4!RpcImpersonateClient` at `0x180062f35`
- `RPCRT4!RpcImpersonateClient` at `0x180062f35`
- `RPCRT4!RpcRevertToSelf` at `0x180062fc1`
- `RPCRT4!RpcRevertToSelf` at `0x1800630b4`
- `RPCRT4!RpcRevertToSelf` at `0x180062fc1`
- `RPCRT4!RpcRevertToSelf` at `0x1800630b4`
- `KERNEL32!GetCurrentThread` at `0x180062f43`
- `KERNEL32!GetCurrentThread` at `0x180062f80`
- `KERNEL32!GetCurrentThread` at `0x180062f43`
- `KERNEL32!GetCurrentThread` at `0x180062f80`
- `KERNEL32!LocalAlloc` at `0x180063018`
- `KERNEL32!LocalAlloc` at `0x180063018`
- `KERNEL32!GetLastError` at `0x180062f6f`
- `KERNEL32!GetLastError` at `0x180062fa9`
- `KERNEL32!GetLastError` at `0x180062ffd`
- `KERNEL32!GetLastError` at `0x180063083`
- `KERNEL32!GetLastError` at `0x180062f6f`
- `KERNEL32!GetLastError` at `0x180062fa9`
- `KERNEL32!GetLastError` at `0x180062ffd`
- `KERNEL32!GetLastError` at `0x180063083`
- `KERNEL32!CloseHandle` at `0x1800630a4`
- `KERNEL32!CloseHandle` at `0x1800630a4`
- `KERNEL32!LocalFree` at `0x180063094`
- `KERNEL32!LocalFree` at `0x180063094`

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
0x180062f00  mov     [rsp-38h+arg_8], rbx
0x180062f05  push    rbp
0x180062f06  push    rsi
0x180062f07  push    rdi
0x180062f08  push    r12
0x180062f0a  push    r13
0x180062f0c  push    r14
0x180062f0e  push    r15
0x180062f10  mov     rbp, rsp
0x180062f13  sub     rsp, 50h
0x180062f17  xor     ebx, ebx
0x180062f19  mov     r15, rcx
0x180062f1c  mov     [r8], bx
0x180062f20  mov     r12, r9
0x180062f23  mov     [rcx], bx
0x180062f26  mov     r14, r8
0x180062f29  xor     ecx, ecx; BindingHandle
0x180062f2b  mov     [rbp+TokenHandle], rbx
0x180062f2f  mov     r13, rdx
0x180062f32  mov     [rbp+arg_10], ebx
0x180062f35  call    cs:__imp_RpcImpersonateClient
0x180062f3c  nop     dword ptr [rax+rax+00h]
0x180062f41  mov     esi, eax
0x180062f43  call    cs:__imp_GetCurrentThread
0x180062f4a  nop     dword ptr [rax+rax+00h]
0x180062f4f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180062f53  xor     r8d, r8d; OpenAsSelf
0x180062f56  mov     rcx, rax; ThreadHandle
0x180062f59  lea     edx, [rbx+8]; DesiredAccess
0x180062f5c  call    cs:__imp_OpenThreadToken
0x180062f63  nop     dword ptr [rax+rax+00h]
0x180062f68  lea     edi, [rbx+1]
0x180062f6b  test    eax, eax
0x180062f6d  jnz     short loc_180062FD2
0x180062f6f  call    cs:__imp_GetLastError
0x180062f76  nop     dword ptr [rax+rax+00h]
0x180062f7b  cmp     eax, 5
0x180062f7e  jnz     short loc_180062FB5
0x180062f80  call    cs:__imp_GetCurrentThread
0x180062f87  nop     dword ptr [rax+rax+00h]
0x180062f8c  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180062f90  mov     r8d, edi; OpenAsSelf
0x180062f93  mov     rcx, rax; ThreadHandle
0x180062f96  lea     edx, [rbx+8]; DesiredAccess
0x180062f99  call    cs:__imp_OpenThreadToken
0x180062fa0  nop     dword ptr [rax+rax+00h]
0x180062fa5  test    eax, eax
0x180062fa7  jnz     short loc_180062FD2
0x180062fa9  call    cs:__imp_GetLastError
0x180062fb0  nop     dword ptr [rax+rax+00h]
0x180062fb5  test    eax, eax
0x180062fb7  jz      short loc_180062FD2
0x180062fb9  test    esi, esi
0x180062fbb  jnz     loc_1800630C4
0x180062fc1  call    cs:__imp_RpcRevertToSelf
0x180062fc8  nop     dword ptr [rax+rax+00h]
0x180062fcd  jmp     loc_1800630C4
0x180062fd2  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180062fd6  lea     rax, [rbp+TokenInformationLength]
0x180062fda  xor     r9d, r9d; TokenInformationLength
0x180062fdd  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180062fe2  xor     r8d, r8d; TokenInformation
0x180062fe5  mov     [rbp+TokenInformationLength], ebx
0x180062fe8  mov     edx, edi; TokenInformationClass
0x180062fea  call    cs:__imp_GetTokenInformation
0x180062ff1  nop     dword ptr [rax+rax+00h]
0x180062ff6  mov     eax, [rbp+TokenInformationLength]
0x180062ff9  test    eax, eax
0x180062ffb  jnz     short loc_180063010
0x180062ffd  call    cs:__imp_GetLastError
0x180063004  nop     dword ptr [rax+rax+00h]
0x180063009  mov     ebx, eax
0x18006300b  jmp     loc_1800630A0
0x180063010  mov     rdx, rax; uBytes
0x180063013  mov     ecx, 40h ; '@'; uFlags
0x180063018  call    cs:__imp_LocalAlloc
0x18006301f  nop     dword ptr [rax+rax+00h]
0x180063024  mov     rdi, rax
0x180063027  test    rax, rax
0x18006302a  jz      short loc_180062FFD
0x18006302c  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180063030  lea     rax, [rbp+TokenInformationLength]
0x180063034  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180063038  mov     r8, rdi; TokenInformation
0x18006303b  mov     edx, 1; TokenInformationClass
0x180063040  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180063045  call    cs:__imp_GetTokenInformation
0x18006304c  nop     dword ptr [rax+rax+00h]
0x180063051  test    eax, eax
0x180063053  jz      short loc_180062FFD
0x180063055  mov     rdx, [rdi]; Sid
0x180063058  lea     rax, [rbp+arg_10]
0x18006305c  mov     [rsp+50h+peUse], rax; peUse
0x180063061  mov     r9, r13; cchName
0x180063064  mov     [rsp+50h+cchReferencedDomainName], r12; cchReferencedDomainName
0x180063069  mov     r8, r15; Name
0x18006306c  xor     ecx, ecx; lpSystemName
0x18006306e  mov     [rsp+50h+ReturnLength], r14; ReferencedDomainName
0x180063073  call    cs:__imp_LookupAccountSidW
0x18006307a  nop     dword ptr [rax+rax+00h]
0x18006307f  test    eax, eax
0x180063081  jnz     short loc_180063091
0x180063083  call    cs:__imp_GetLastError
0x18006308a  nop     dword ptr [rax+rax+00h]
0x18006308f  mov     ebx, eax
0x180063091  mov     rcx, rdi; hMem
0x180063094  call    cs:__imp_LocalFree
0x18006309b  nop     dword ptr [rax+rax+00h]
0x1800630a0  mov     rcx, [rbp+TokenHandle]; hObject
0x1800630a4  call    cs:__imp_CloseHandle
0x1800630ab  nop     dword ptr [rax+rax+00h]
0x1800630b0  test    esi, esi
0x1800630b2  jnz     short loc_1800630C2
0x1800630b4  call    cs:__imp_RpcRevertToSelf
0x1800630bb  nop     dword ptr [rax+rax+00h]
0x1800630c0  mov     ebx, eax
0x1800630c2  mov     eax, ebx
0x1800630c4  mov     rbx, [rsp+50h+arg_8]
0x1800630cc  add     rsp, 50h
0x1800630d0  pop     r15
0x1800630d2  pop     r14
0x1800630d4  pop     r13
0x1800630d6  pop     r12
0x1800630d8  pop     rdi
0x1800630d9  pop     rsi
0x1800630da  pop     rbp
0x1800630db  retn
```
