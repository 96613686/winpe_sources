# FwGetRpcClientAppContainerSid(void *,_TOKEN_APPCONTAINER_INFORMATION * *)

- ea: `0x1800515e8`
- end: `0x18005175b`
- name: `?FwGetRpcClientAppContainerSid@@YAJPEAXPEAPEAU_TOKEN_APPCONTAINER_INFORMATION@@@Z`
- size: `371`
- prototype: `__int64 __fastcall(void *, struct _TOKEN_APPCONTAINER_INFORMATION **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800511b4`

## callees

- `0x18000a710`
- `0x1800515e8`
- `0x1800729c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180051663`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180051663`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005167d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005167d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005168d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005168d`
- `RPCRT4!RpcImpersonateClient` at `0x180051612`
- `RPCRT4!RpcImpersonateClient` at `0x180051612`
- `RPCRT4!RpcRevertToSelf` at `0x18005172f`
- `RPCRT4!RpcRevertToSelf` at `0x18005172f`
- `fwbase!FwGetTokenInformation` at `0x1800516d7`
- `fwbase!FwGetTokenInformation` at `0x1800516d7`
- `fwbase!FwCloseHandle` at `0x18005171f`
- `fwbase!FwCloseHandle` at `0x18005171f`

## pseudocode

```c
__int64 __fastcall FwGetRpcClientAppContainerSid(void *a1, struct _TOKEN_APPCONTAINER_INFORMATION **a2)
{
  RPC_STATUS v3; // eax
  unsigned int TokenInformation; // ebx
  int v5; // edi
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
      v7 = 25;
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
      TokenInformation = FwGetTokenInformation(TokenHandle, 31, a2, 0);
      if ( (TokenInformation & 0x80000000) != 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v7 = 27;
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
        v7 = 26;
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
0x1800515e8  mov     [rsp+arg_10], rbx
0x1800515ed  mov     [rsp+arg_18], rsi
0x1800515f2  push    rdi
0x1800515f3  sub     rsp, 30h
0x1800515f7  mov     rax, cs:__security_cookie
0x1800515fe  xor     rax, rsp
0x180051601  mov     [rsp+38h+var_10], rax
0x180051606  mov     rsi, rdx
0x180051609  mov     [rsp+38h+TokenHandle], 0
0x180051612  call    cs:__imp_RpcImpersonateClient
0x180051619  nop     dword ptr [rax+rax+00h]
0x18005161e  mov     ebx, eax
0x180051620  test    eax, eax
0x180051622  jz      short loc_18005165E
0x180051624  xor     edi, edi
0x180051626  test    eax, eax
0x180051628  jle     short loc_180051633
0x18005162a  movzx   ebx, ax
0x18005162d  or      ebx, 80070000h
0x180051633  mov     rcx, cs:WPP_GLOBAL_Control
0x18005163a  lea     rax, WPP_GLOBAL_Control
0x180051641  cmp     rcx, rax
0x180051644  jz      loc_18005171A
0x18005164a  test    byte ptr [rcx+1Ch], 1
0x18005164e  jz      loc_18005171A
0x180051654  mov     edx, 19h
0x180051659  jmp     loc_180051707
0x18005165e  mov     edi, 1
0x180051663  call    cs:__imp_GetCurrentThread
0x18005166a  nop     dword ptr [rax+rax+00h]
0x18005166f  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180051674  mov     r8d, edi; OpenAsSelf
0x180051677  mov     rcx, rax; ThreadHandle
0x18005167a  lea     edx, [rdi+7]; DesiredAccess
0x18005167d  call    cs:__imp_OpenThreadToken
0x180051684  nop     dword ptr [rax+rax+00h]
0x180051689  test    eax, eax
0x18005168b  jnz     short loc_1800516C8
0x18005168d  call    cs:__imp_GetLastError
0x180051694  nop     dword ptr [rax+rax+00h]
0x180051699  mov     ebx, eax
0x18005169b  test    eax, eax
0x18005169d  jle     short loc_1800516A8
0x18005169f  movzx   ebx, ax
0x1800516a2  or      ebx, 80070000h
0x1800516a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800516af  lea     rax, WPP_GLOBAL_Control
0x1800516b6  cmp     rcx, rax
0x1800516b9  jz      short loc_18005171A
0x1800516bb  test    [rcx+1Ch], dil
0x1800516bf  jz      short loc_18005171A
0x1800516c1  mov     edx, 1Ah
0x1800516c6  jmp     short loc_180051707
0x1800516c8  mov     rcx, [rsp+38h+TokenHandle]
0x1800516cd  xor     r9d, r9d
0x1800516d0  mov     r8, rsi
0x1800516d3  lea     edx, [r9+1Fh]
0x1800516d7  call    cs:__imp_FwGetTokenInformation
0x1800516de  nop     dword ptr [rax+rax+00h]
0x1800516e3  mov     ebx, eax
0x1800516e5  test    eax, eax
0x1800516e7  jns     short loc_18005171A
0x1800516e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800516f0  lea     rax, WPP_GLOBAL_Control
0x1800516f7  cmp     rcx, rax
0x1800516fa  jz      short loc_18005171A
0x1800516fc  test    [rcx+1Ch], dil
0x180051700  jz      short loc_18005171A
0x180051702  mov     edx, 1Bh
0x180051707  mov     rcx, [rcx+10h]
0x18005170b  lea     r8, WPP_a875d200678f3c386c19a36d1916a086_Traceguids
0x180051712  mov     r9d, ebx
0x180051715  call    WPP_SF_d
0x18005171a  mov     rcx, [rsp+38h+TokenHandle]
0x18005171f  call    cs:__imp_FwCloseHandle
0x180051726  nop     dword ptr [rax+rax+00h]
0x18005172b  test    edi, edi
0x18005172d  jz      short loc_18005173B
0x18005172f  call    cs:__imp_RpcRevertToSelf
0x180051736  nop     dword ptr [rax+rax+00h]
0x18005173b  mov     eax, ebx
0x18005173d  mov     rcx, [rsp+38h+var_10]
0x180051742  xor     rcx, rsp; StackCookie
0x180051745  call    __security_check_cookie
0x18005174a  mov     rbx, [rsp+38h+arg_10]
0x18005174f  mov     rsi, [rsp+38h+arg_18]
0x180051754  add     rsp, 30h
0x180051758  pop     rdi
0x180051759  retn
```
