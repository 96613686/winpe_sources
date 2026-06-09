# RpcAdminCheck

- ea: `0x180069568`
- end: `0x180069708`
- name: `RpcAdminCheck`
- size: `416`
- prototype: `__int64 __fastcall(PBOOL IsMember)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180069260`
- `0x1800692e0`
- `0x180069340`

## callees

- `0x18000d7c0`
- `0x18004b5f0`
- `0x180069568`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800695b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069695`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800695b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069695`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800696d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800696d5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800696c0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800696c0`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180069653`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180069653`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180069685`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180069685`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800695dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800695dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800695f8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800695f8`
- `RPCRT4!RpcImpersonateClient` at `0x1800695a5`
- `RPCRT4!RpcImpersonateClient` at `0x1800695a5`
- `RPCRT4!RpcRevertToSelf` at `0x1800696e1`
- `RPCRT4!RpcRevertToSelf` at `0x1800696e1`

## string_xrefs

- `0x1800695c1`: `RpcImpersonateClient failed with error %d`
- `0x180069614`: `OpenThreadToken failed with error %d`
- `0x18006966f`: `AllocateAndInitializeSid returned error %x`

## pseudocode

```c
__int64 __fastcall RpcAdminCheck(PBOOL IsMember)
{
  __int64 LastError; // rbx
  HANDLE CurrentThread; // rax
  DWORD v4; // eax
  const wchar_t *v5; // rdx
  PSID SidToCheck; // [rsp+60h] [rbp+17h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+1Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  TokenHandle = (void *)-1LL;
  if ( RpcImpersonateClient(0) )
  {
    LastError = GetLastError();
    EventWrite0(0x800000, L"RpcImpersonateClient failed with error %d", LastError);
    return (unsigned int)LastError;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v4 = GetLastError();
    v5 = L"OpenThreadToken failed with error %d";
LABEL_9:
    LODWORD(LastError) = v4;
    EventWrite0(0x800000, v5, v4);
    goto LABEL_10;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    v4 = GetLastError();
    v5 = L"AllocateAndInitializeSid returned error %x";
    goto LABEL_9;
  }
  LODWORD(LastError) = 0;
  if ( !CheckTokenMembership(TokenHandle, SidToCheck, IsMember) )
  {
    v4 = GetLastError();
    v5 = L"Admin check failed with error %u";
    goto LABEL_9;
  }
LABEL_10:
  if ( SidToCheck )
    FreeSid(SidToCheck);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  RpcRevertToSelf();
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180069568  push    rbp
0x18006956a  push    rbx
0x18006956b  push    rsi
0x18006956c  push    rdi
0x18006956d  lea     rbp, [rsp-3Fh]
0x180069572  sub     rsp, 88h
0x180069579  mov     rax, cs:__security_cookie
0x180069580  xor     rax, rsp
0x180069583  mov     [rbp+57h+var_28], rax
0x180069587  xor     esi, esi
0x180069589  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18006958f  mov     [rcx], esi
0x180069591  mov     rdi, rcx
0x180069594  xor     ecx, ecx; BindingHandle
0x180069596  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x180069599  mov     [rbp+57h+SidToCheck], rsi
0x18006959d  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800695a5  call    cs:__imp_RpcImpersonateClient
0x1800695ac  nop     dword ptr [rax+rax+00h]
0x1800695b1  test    eax, eax
0x1800695b3  jz      short loc_1800695DC
0x1800695b5  call    cs:__imp_GetLastError
0x1800695bc  nop     dword ptr [rax+rax+00h]
0x1800695c1  lea     rdx, aRpcimpersonate_0; "RpcImpersonateClient failed with error "...
0x1800695c8  mov     ecx, 800000h
0x1800695cd  mov     r8d, eax
0x1800695d0  mov     ebx, eax
0x1800695d2  call    EventWrite0
0x1800695d7  jmp     loc_1800696ED
0x1800695dc  call    cs:__imp_GetCurrentThread
0x1800695e3  nop     dword ptr [rax+rax+00h]
0x1800695e8  mov     edx, 8; DesiredAccess
0x1800695ed  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800695f1  mov     rcx, rax; ThreadHandle
0x1800695f4  lea     r8d, [rdx-7]; OpenAsSelf
0x1800695f8  call    cs:__imp_OpenThreadToken
0x1800695ff  nop     dword ptr [rax+rax+00h]
0x180069604  test    eax, eax
0x180069606  jnz     short loc_180069620
0x180069608  call    cs:__imp_GetLastError
0x18006960f  nop     dword ptr [rax+rax+00h]
0x180069614  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed with error %d"
0x18006961b  jmp     loc_1800696A8
0x180069620  lea     rax, [rbp+57h+SidToCheck]
0x180069624  mov     r9d, 220h; nSubAuthority1
0x18006962a  mov     [rsp+0A0h+pSid], rax; pSid
0x18006962f  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180069633  mov     [rsp+0A0h+nSubAuthority7], esi; nSubAuthority7
0x180069637  mov     r8d, 20h ; ' '; nSubAuthority0
0x18006963d  mov     [rsp+0A0h+nSubAuthority6], esi; nSubAuthority6
0x180069641  mov     dl, 2; nSubAuthorityCount
0x180069643  mov     [rsp+0A0h+nSubAuthority5], esi; nSubAuthority5
0x180069647  mov     [rsp+0A0h+nSubAuthority4], esi; nSubAuthority4
0x18006964b  mov     [rsp+0A0h+nSubAuthority3], esi; nSubAuthority3
0x18006964f  mov     [rsp+0A0h+nSubAuthority2], esi; nSubAuthority2
0x180069653  call    cs:__imp_AllocateAndInitializeSid
0x18006965a  nop     dword ptr [rax+rax+00h]
0x18006965f  test    eax, eax
0x180069661  jnz     short loc_180069678
0x180069663  call    cs:__imp_GetLastError
0x18006966a  nop     dword ptr [rax+rax+00h]
0x18006966f  lea     rdx, aAllocateandini; "AllocateAndInitializeSid returned error"...
0x180069676  jmp     short loc_1800696A8
0x180069678  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18006967c  mov     r8, rdi; IsMember
0x18006967f  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180069683  mov     ebx, esi
0x180069685  call    cs:__imp_CheckTokenMembership
0x18006968c  nop     dword ptr [rax+rax+00h]
0x180069691  test    eax, eax
0x180069693  jnz     short loc_1800696B7
0x180069695  call    cs:__imp_GetLastError
0x18006969c  nop     dword ptr [rax+rax+00h]
0x1800696a1  lea     rdx, aAdminCheckFail; "Admin check failed with error %u"
0x1800696a8  mov     r8d, eax
0x1800696ab  mov     ecx, 800000h
0x1800696b0  mov     ebx, eax
0x1800696b2  call    EventWrite0
0x1800696b7  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x1800696bb  test    rcx, rcx
0x1800696be  jz      short loc_1800696CC
0x1800696c0  call    cs:__imp_FreeSid
0x1800696c7  nop     dword ptr [rax+rax+00h]
0x1800696cc  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800696d0  test    rcx, rcx
0x1800696d3  jz      short loc_1800696E1
0x1800696d5  call    cs:__imp_CloseHandle
0x1800696dc  nop     dword ptr [rax+rax+00h]
0x1800696e1  call    cs:__imp_RpcRevertToSelf
0x1800696e8  nop     dword ptr [rax+rax+00h]
0x1800696ed  mov     eax, ebx
0x1800696ef  mov     rcx, [rbp+57h+var_28]
0x1800696f3  xor     rcx, rsp; StackCookie
0x1800696f6  call    __security_check_cookie
0x1800696fb  add     rsp, 88h
0x180069702  pop     rdi
0x180069703  pop     rsi
0x180069704  pop     rbx
0x180069705  pop     rbp
0x180069706  retn
```
