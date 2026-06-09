# FwGetRPCClientUserSid(void *,_TOKEN_USER * *)

- ea: `0x180051470`
- end: `0x1800515e1`
- name: `?FwGetRPCClientUserSid@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(void *, struct _TOKEN_USER **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800511b4`

## callees

- `0x18000a710`
- `0x180051470`
- `0x1800729c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800514eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800514eb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180051505`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180051505`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051515`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051515`
- `RPCRT4!RpcImpersonateClient` at `0x18005149a`
- `RPCRT4!RpcImpersonateClient` at `0x18005149a`
- `RPCRT4!RpcRevertToSelf` at `0x1800515b5`
- `RPCRT4!RpcRevertToSelf` at `0x1800515b5`
- `fwbase!FwGetTokenInformation` at `0x18005155d`
- `fwbase!FwGetTokenInformation` at `0x18005155d`
- `fwbase!FwCloseHandle` at `0x1800515a5`
- `fwbase!FwCloseHandle` at `0x1800515a5`

## pseudocode

```c
__int64 __fastcall FwGetRPCClientUserSid(void *a1, struct _TOKEN_USER **a2)
{
  RPC_STATUS v3; // eax
  unsigned int TokenInformation; // ebx
  int v5; // esi
  __int64 v6; // rcx
  __int64 v7; // rdx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  void *TokenHandle; // [rsp+20h] [rbp-18h] BYREF

  TokenHandle = 0;
  v3 = RpcImpersonateClient(a1);
  TokenInformation = v3;
  if ( v3 )
  {
    v5 = 0;
    if ( v3 > 0 )
      TokenInformation = (unsigned __int16)v3 | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v7 = 22;
LABEL_17:
      WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_a875d200678f3c386c19a36d1916a086_Traceguids, TokenInformation);
    }
  }
  else
  {
    v5 = 1;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      TokenInformation = FwGetTokenInformation(TokenHandle, 1, a2, 0);
      if ( (TokenInformation & 0x80000000) != 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v7 = 24;
          goto LABEL_17;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      TokenInformation = LastError;
      if ( LastError > 0 )
        TokenInformation = (unsigned __int16)LastError | 0x80070000;
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v7 = 23;
        goto LABEL_17;
      }
    }
  }
  FwCloseHandle(TokenHandle);
  if ( v5 )
    RpcRevertToSelf();
  return TokenInformation;
}

```

## disassembly

```asm
0x180051470  mov     [rsp+arg_10], rbx
0x180051475  mov     [rsp+arg_18], rbp
0x18005147a  push    rsi
0x18005147b  sub     rsp, 30h
0x18005147f  mov     rax, cs:__security_cookie
0x180051486  xor     rax, rsp
0x180051489  mov     [rsp+38h+var_10], rax
0x18005148e  mov     rbp, rdx
0x180051491  mov     [rsp+38h+TokenHandle], 0
0x18005149a  call    cs:__imp_RpcImpersonateClient
0x1800514a1  nop     dword ptr [rax+rax+00h]
0x1800514a6  mov     ebx, eax
0x1800514a8  test    eax, eax
0x1800514aa  jz      short loc_1800514E6
0x1800514ac  xor     esi, esi
0x1800514ae  test    eax, eax
0x1800514b0  jle     short loc_1800514BB
0x1800514b2  movzx   ebx, ax
0x1800514b5  or      ebx, 80070000h
0x1800514bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800514c2  lea     rax, WPP_GLOBAL_Control
0x1800514c9  cmp     rcx, rax
0x1800514cc  jz      loc_1800515A0
0x1800514d2  test    byte ptr [rcx+1Ch], 1
0x1800514d6  jz      loc_1800515A0
0x1800514dc  mov     edx, 16h
0x1800514e1  jmp     loc_18005158D
0x1800514e6  mov     esi, 1
0x1800514eb  call    cs:__imp_GetCurrentThread
0x1800514f2  nop     dword ptr [rax+rax+00h]
0x1800514f7  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800514fc  mov     r8d, esi; OpenAsSelf
0x1800514ff  mov     rcx, rax; ThreadHandle
0x180051502  lea     edx, [rsi+7]; DesiredAccess
0x180051505  call    cs:__imp_OpenThreadToken
0x18005150c  nop     dword ptr [rax+rax+00h]
0x180051511  test    eax, eax
0x180051513  jnz     short loc_180051550
0x180051515  call    cs:__imp_GetLastError
0x18005151c  nop     dword ptr [rax+rax+00h]
0x180051521  mov     ebx, eax
0x180051523  test    eax, eax
0x180051525  jle     short loc_180051530
0x180051527  movzx   ebx, ax
0x18005152a  or      ebx, 80070000h
0x180051530  mov     rcx, cs:WPP_GLOBAL_Control
0x180051537  lea     rax, WPP_GLOBAL_Control
0x18005153e  cmp     rcx, rax
0x180051541  jz      short loc_1800515A0
0x180051543  test    [rcx+1Ch], sil
0x180051547  jz      short loc_1800515A0
0x180051549  mov     edx, 17h
0x18005154e  jmp     short loc_18005158D
0x180051550  mov     rcx, [rsp+38h+TokenHandle]
0x180051555  xor     r9d, r9d
0x180051558  mov     r8, rbp
0x18005155b  mov     edx, esi
0x18005155d  call    cs:__imp_FwGetTokenInformation
0x180051564  nop     dword ptr [rax+rax+00h]
0x180051569  mov     ebx, eax
0x18005156b  test    eax, eax
0x18005156d  jns     short loc_1800515A0
0x18005156f  mov     rcx, cs:WPP_GLOBAL_Control
0x180051576  lea     rax, WPP_GLOBAL_Control
0x18005157d  cmp     rcx, rax
0x180051580  jz      short loc_1800515A0
0x180051582  test    [rcx+1Ch], sil
0x180051586  jz      short loc_1800515A0
0x180051588  mov     edx, 18h
0x18005158d  mov     rcx, [rcx+10h]
0x180051591  lea     r8, WPP_a875d200678f3c386c19a36d1916a086_Traceguids
0x180051598  mov     r9d, ebx
0x18005159b  call    WPP_SF_d
0x1800515a0  mov     rcx, [rsp+38h+TokenHandle]
0x1800515a5  call    cs:__imp_FwCloseHandle
0x1800515ac  nop     dword ptr [rax+rax+00h]
0x1800515b1  test    esi, esi
0x1800515b3  jz      short loc_1800515C1
0x1800515b5  call    cs:__imp_RpcRevertToSelf
0x1800515bc  nop     dword ptr [rax+rax+00h]
0x1800515c1  mov     eax, ebx
0x1800515c3  mov     rcx, [rsp+38h+var_10]
0x1800515c8  xor     rcx, rsp; StackCookie
0x1800515cb  call    __security_check_cookie
0x1800515d0  mov     rbx, [rsp+38h+arg_10]
0x1800515d5  mov     rbp, [rsp+38h+arg_18]
0x1800515da  add     rsp, 30h
0x1800515de  pop     rsi
0x1800515df  retn
```
