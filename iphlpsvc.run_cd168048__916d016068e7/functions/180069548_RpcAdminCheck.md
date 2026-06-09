# RpcAdminCheck

- ea: `0x180069548`
- end: `0x1800696e8`
- name: `RpcAdminCheck`
- size: `416`
- prototype: `__int64 __fastcall(PBOOL IsMember)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180069240`
- `0x1800692c0`
- `0x180069320`

## callees

- `0x18000d7b0`
- `0x18004b630`
- `0x180069548`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069595`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800695e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069675`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069595`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800695e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069675`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800696b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800696b5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800696a0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800696a0`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180069633`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180069633`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180069665`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180069665`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800695bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800695bc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800695d8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800695d8`
- `RPCRT4!RpcImpersonateClient` at `0x180069585`
- `RPCRT4!RpcImpersonateClient` at `0x180069585`
- `RPCRT4!RpcRevertToSelf` at `0x1800696c1`
- `RPCRT4!RpcRevertToSelf` at `0x1800696c1`

## string_xrefs

- `0x1800695a1`: `RpcImpersonateClient failed with error %d`
- `0x1800695f4`: `OpenThreadToken failed with error %d`
- `0x18006964f`: `AllocateAndInitializeSid returned error %x`

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
0x180069548  push    rbp
0x18006954a  push    rbx
0x18006954b  push    rsi
0x18006954c  push    rdi
0x18006954d  lea     rbp, [rsp-3Fh]
0x180069552  sub     rsp, 88h
0x180069559  mov     rax, cs:__security_cookie
0x180069560  xor     rax, rsp
0x180069563  mov     [rbp+57h+var_28], rax
0x180069567  xor     esi, esi
0x180069569  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18006956f  mov     [rcx], esi
0x180069571  mov     rdi, rcx
0x180069574  xor     ecx, ecx; BindingHandle
0x180069576  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x180069579  mov     [rbp+57h+SidToCheck], rsi
0x18006957d  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180069585  call    cs:__imp_RpcImpersonateClient
0x18006958c  nop     dword ptr [rax+rax+00h]
0x180069591  test    eax, eax
0x180069593  jz      short loc_1800695BC
0x180069595  call    cs:__imp_GetLastError
0x18006959c  nop     dword ptr [rax+rax+00h]
0x1800695a1  lea     rdx, aRpcimpersonate_0; "RpcImpersonateClient failed with error "...
0x1800695a8  mov     ecx, 800000h
0x1800695ad  mov     r8d, eax
0x1800695b0  mov     ebx, eax
0x1800695b2  call    EventWrite0
0x1800695b7  jmp     loc_1800696CD
0x1800695bc  call    cs:__imp_GetCurrentThread
0x1800695c3  nop     dword ptr [rax+rax+00h]
0x1800695c8  mov     edx, 8; DesiredAccess
0x1800695cd  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800695d1  mov     rcx, rax; ThreadHandle
0x1800695d4  lea     r8d, [rdx-7]; OpenAsSelf
0x1800695d8  call    cs:__imp_OpenThreadToken
0x1800695df  nop     dword ptr [rax+rax+00h]
0x1800695e4  test    eax, eax
0x1800695e6  jnz     short loc_180069600
0x1800695e8  call    cs:__imp_GetLastError
0x1800695ef  nop     dword ptr [rax+rax+00h]
0x1800695f4  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed with error %d"
0x1800695fb  jmp     loc_180069688
0x180069600  lea     rax, [rbp+57h+SidToCheck]
0x180069604  mov     r9d, 220h; nSubAuthority1
0x18006960a  mov     [rsp+0A0h+pSid], rax; pSid
0x18006960f  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180069613  mov     [rsp+0A0h+nSubAuthority7], esi; nSubAuthority7
0x180069617  mov     r8d, 20h ; ' '; nSubAuthority0
0x18006961d  mov     [rsp+0A0h+nSubAuthority6], esi; nSubAuthority6
0x180069621  mov     dl, 2; nSubAuthorityCount
0x180069623  mov     [rsp+0A0h+nSubAuthority5], esi; nSubAuthority5
0x180069627  mov     [rsp+0A0h+nSubAuthority4], esi; nSubAuthority4
0x18006962b  mov     [rsp+0A0h+nSubAuthority3], esi; nSubAuthority3
0x18006962f  mov     [rsp+0A0h+nSubAuthority2], esi; nSubAuthority2
0x180069633  call    cs:__imp_AllocateAndInitializeSid
0x18006963a  nop     dword ptr [rax+rax+00h]
0x18006963f  test    eax, eax
0x180069641  jnz     short loc_180069658
0x180069643  call    cs:__imp_GetLastError
0x18006964a  nop     dword ptr [rax+rax+00h]
0x18006964f  lea     rdx, aAllocateandini; "AllocateAndInitializeSid returned error"...
0x180069656  jmp     short loc_180069688
0x180069658  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18006965c  mov     r8, rdi; IsMember
0x18006965f  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180069663  mov     ebx, esi
0x180069665  call    cs:__imp_CheckTokenMembership
0x18006966c  nop     dword ptr [rax+rax+00h]
0x180069671  test    eax, eax
0x180069673  jnz     short loc_180069697
0x180069675  call    cs:__imp_GetLastError
0x18006967c  nop     dword ptr [rax+rax+00h]
0x180069681  lea     rdx, aAdminCheckFail; "Admin check failed with error %u"
0x180069688  mov     r8d, eax
0x18006968b  mov     ecx, 800000h
0x180069690  mov     ebx, eax
0x180069692  call    EventWrite0
0x180069697  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18006969b  test    rcx, rcx
0x18006969e  jz      short loc_1800696AC
0x1800696a0  call    cs:__imp_FreeSid
0x1800696a7  nop     dword ptr [rax+rax+00h]
0x1800696ac  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800696b0  test    rcx, rcx
0x1800696b3  jz      short loc_1800696C1
0x1800696b5  call    cs:__imp_CloseHandle
0x1800696bc  nop     dword ptr [rax+rax+00h]
0x1800696c1  call    cs:__imp_RpcRevertToSelf
0x1800696c8  nop     dword ptr [rax+rax+00h]
0x1800696cd  mov     eax, ebx
0x1800696cf  mov     rcx, [rbp+57h+var_28]
0x1800696d3  xor     rcx, rsp; StackCookie
0x1800696d6  call    __security_check_cookie
0x1800696db  add     rsp, 88h
0x1800696e2  pop     rdi
0x1800696e3  pop     rsi
0x1800696e4  pop     rbx
0x1800696e5  pop     rbp
0x1800696e6  retn
```
