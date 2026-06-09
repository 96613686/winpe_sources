# IsRpcAccessAllowed(void)

- ea: `0x18002ef0c`
- end: `0x18002f150`
- name: `?IsRpcAccessAllowed@@YA_NXZ`
- size: `580`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019fb0`
- `0x18001a180`

## callees

- `0x180020d20`
- `0x18002ef0c`
- `0x1800307cc`
- `0x1800327c0`
- `0x1800713b8`
- `0x1800a88a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002ef6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002ef6f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002ef88`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002ef88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f133`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f13e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f133`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f13e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002f0ab`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002f0c0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002f0ab`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002f0c0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002efeb`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002efeb`
- `RPCRT4!RpcRevertToSelfEx` at `0x18002f027`
- `RPCRT4!RpcRevertToSelfEx` at `0x18002f081`
- `RPCRT4!RpcRevertToSelfEx` at `0x18002f0f1`
- `RPCRT4!RpcRevertToSelfEx` at `0x18002f027`
- `RPCRT4!RpcRevertToSelfEx` at `0x18002f081`
- `RPCRT4!RpcRevertToSelfEx` at `0x18002f0f1`
- `RPCRT4!RpcImpersonateClient` at `0x18002ef28`
- `RPCRT4!RpcImpersonateClient` at `0x18002ef28`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002efc6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002efc6`

## string_xrefs

- `0x18002ef3a`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsserver.cpp`
- `0x18002f039`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsserver.cpp`
- `0x18002f05c`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsserver.cpp`
- `0x18002f093`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsserver.cpp`
- `0x18002f0d4`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsserver.cpp`
- `0x18002f103`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsserver.cpp`
- `0x18002f120`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsserver.cpp`

## pseudocode

```c
bool IsRpcAccessAllowed(void)
{
  unsigned int v0; // eax
  const char *v1; // r9
  bool result; // al
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  unsigned int *i; // rdi
  const char *v6; // r9
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10[2]; // [rsp+20h] [rbp-38h] BYREF
  WINBOOL IsMember; // [rsp+28h] [rbp-30h] BYREF
  PSID Sid; // [rsp+30h] [rbp-28h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v0 = RpcImpersonateClient(0);
  if ( v0 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x4A,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsserver.cpp",
      (const char *)v0,
      v10[0]);
    result = 0;
  }
  else
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
    {
      *(_QWORD *)v10 = L"S-1-5-80-1428027539-3309602793-2678353003-1498846795-3763184142";
      for ( i = v10; i != (unsigned int *)&IsMember; i += 2 )
      {
        Sid = 0;
        if ( ConvertStringSidToSidW(*(LPCWSTR *)i, &Sid) )
        {
          IsMember = 0;
          if ( CheckTokenMembership(TokenHandle, Sid, &IsMember) && IsMember )
          {
            if ( Sid )
              FreeSid(Sid);
            if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(TokenHandle);
            v7 = RpcRevertToSelfEx(0);
            if ( v7 )
              wil::details::in1diag3::_Log_Win32(
                retaddr,
                (void *)0x4F,
                (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsserver.cpp",
                (const char *)v7,
                v10[0]);
            result = 1;
            goto LABEL_28;
          }
        }
        else
        {
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0x60,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsserver.cpp",
            v6);
        }
        if ( Sid )
          FreeSid(Sid);
      }
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsserver.cpp",
        (const char *)5,
        v10[0]);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      v8 = RpcRevertToSelfEx(0);
      if ( v8 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x4F,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsserver.cpp",
          (const char *)v8,
          v10[0]);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsserver.cpp",
        v4);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      v9 = RpcRevertToSelfEx(0);
      if ( v9 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x4F,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsserver.cpp",
          (const char *)v9,
          v10[0]);
      result = 0;
    }
  }
LABEL_28:
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsserver.cpp",
        v1);
      result = 0;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x18002ef0c  mov     [rsp+arg_0], rdi
0x18002ef11  push    r14
0x18002ef13  sub     rsp, 50h
0x18002ef17  mov     rax, cs:__security_cookie
0x18002ef1e  xor     rax, rsp
0x18002ef21  mov     [rsp+58h+var_18], rax
0x18002ef26  xor     ecx, ecx; BindingHandle
0x18002ef28  call    cs:__imp_RpcImpersonateClient
0x18002ef2e  mov     rcx, [rsp+58h]; this
0x18002ef33  test    eax, eax
0x18002ef35  jz      short loc_18002EF66
0x18002ef37  mov     r9d, eax; char *
0x18002ef3a  lea     r8, aOnecoreNetNetp_14; "onecore\\net\\netprofiles\\service\\src"...
0x18002ef41  mov     edx, 4Ah ; 'J'; void *
0x18002ef46  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002ef4b  xor     al, al
0x18002ef4d  mov     rcx, [rsp+58h+var_18]
0x18002ef52  xor     rcx, rsp; StackCookie
0x18002ef55  call    __security_check_cookie
0x18002ef5a  mov     rdi, [rsp+58h+arg_0]
0x18002ef5f  add     rsp, 50h
0x18002ef63  pop     r14
0x18002ef65  retn
0x18002ef66  mov     [rsp+58h+TokenHandle], 0
0x18002ef6f  call    cs:__imp_GetCurrentThread
0x18002ef75  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x18002ef7a  mov     edx, 0F01FFh; DesiredAccess
0x18002ef7f  mov     r8d, 1; OpenAsSelf
0x18002ef85  mov     rcx, rax; ThreadHandle
0x18002ef88  call    cs:__imp_OpenThreadToken
0x18002ef8e  test    eax, eax
0x18002ef90  jz      loc_18002F0CF
0x18002ef96  lea     rax, aS1580142802753; "S-1-5-80-1428027539-3309602793-26783530"...
0x18002ef9d  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x18002efa2  lea     rdi, [rsp+58h+var_38]
0x18002efa7  lea     r14, [rsp+58h+IsMember]
0x18002efac  cmp     rdi, r14
0x18002efaf  jz      loc_18002F051
0x18002efb5  mov     [rsp+58h+Sid], 0
0x18002efbe  lea     rdx, [rsp+58h+Sid]; Sid
0x18002efc3  mov     rcx, [rdi]; StringSid
0x18002efc6  call    cs:__imp_ConvertStringSidToSidW
0x18002efcc  test    eax, eax
0x18002efce  jz      loc_18002F11B
0x18002efd4  mov     [rsp+58h+IsMember], 0
0x18002efdc  lea     r8, [rsp+58h+IsMember]; IsMember
0x18002efe1  mov     rdx, [rsp+58h+Sid]; SidToCheck
0x18002efe6  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18002efeb  call    cs:__imp_CheckTokenMembership
0x18002eff1  test    eax, eax
0x18002eff3  jz      loc_18002F0B6
0x18002eff9  cmp     [rsp+58h+IsMember], 0
0x18002effe  jz      loc_18002F0B6
0x18002f004  mov     rcx, [rsp+58h+Sid]; pSid
0x18002f009  test    rcx, rcx
0x18002f00c  jnz     loc_18002F0AB
0x18002f012  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18002f017  lea     rax, [rcx-1]
0x18002f01b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002f01f  jbe     loc_18002F133
0x18002f025  xor     ecx, ecx; BindingHandle
0x18002f027  call    cs:__imp_RpcRevertToSelfEx
0x18002f02d  mov     rcx, [rsp+58h]; this
0x18002f032  test    eax, eax
0x18002f034  jz      short loc_18002F04A
0x18002f036  mov     r9d, eax; char *
0x18002f039  lea     r8, aOnecoreNetNetp_14; "onecore\\net\\netprofiles\\service\\src"...
0x18002f040  mov     edx, 4Fh ; 'O'; void *
0x18002f045  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002f04a  mov     al, 1
0x18002f04c  jmp     loc_18002EF4D
0x18002f051  mov     rcx, [rsp+58h]; this
0x18002f056  mov     r9d, 5; char *
0x18002f05c  lea     r8, aOnecoreNetNetp_14; "onecore\\net\\netprofiles\\service\\src"...
0x18002f063  lea     edx, [r9+66h]; void *
0x18002f067  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18002f06c  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18002f071  lea     rax, [rcx-1]
0x18002f075  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002f079  jbe     loc_18002F13E
0x18002f07f  xor     ecx, ecx; BindingHandle
0x18002f081  call    cs:__imp_RpcRevertToSelfEx
0x18002f087  mov     rcx, [rsp+58h]; this
0x18002f08c  test    eax, eax
0x18002f08e  jz      short loc_18002F0A4
0x18002f090  mov     r9d, eax; char *
0x18002f093  lea     r8, aOnecoreNetNetp_14; "onecore\\net\\netprofiles\\service\\src"...
0x18002f09a  mov     edx, 4Fh ; 'O'; void *
0x18002f09f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002f0a4  xor     al, al
0x18002f0a6  jmp     loc_18002EF4D
0x18002f0ab  call    cs:__imp_FreeSid
0x18002f0b1  jmp     loc_18002F012
0x18002f0b6  mov     rcx, [rsp+58h+Sid]; pSid
0x18002f0bb  test    rcx, rcx
0x18002f0be  jz      short loc_18002F0C6
0x18002f0c0  call    cs:__imp_FreeSid
0x18002f0c6  add     rdi, 8
0x18002f0ca  jmp     loc_18002EFAC
0x18002f0cf  mov     rcx, [rsp+58h]; this
0x18002f0d4  lea     r8, aOnecoreNetNetp_14; "onecore\\net\\netprofiles\\service\\src"...
0x18002f0db  mov     edx, 54h ; 'T'; void *
0x18002f0e0  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002f0e5  lea     rcx, [rsp+58h+TokenHandle]
0x18002f0ea  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f0ef  xor     ecx, ecx; BindingHandle
0x18002f0f1  call    cs:__imp_RpcRevertToSelfEx
0x18002f0f7  mov     rcx, [rsp+58h]; this
0x18002f0fc  test    eax, eax
0x18002f0fe  jz      short loc_18002F114
0x18002f100  mov     r9d, eax; char *
0x18002f103  lea     r8, aOnecoreNetNetp_14; "onecore\\net\\netprofiles\\service\\src"...
0x18002f10a  mov     edx, 4Fh ; 'O'; void *
0x18002f10f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002f114  xor     al, al
0x18002f116  jmp     loc_18002EF4D
0x18002f11b  mov     rcx, [rsp+58h]; this
0x18002f120  lea     r8, aOnecoreNetNetp_14; "onecore\\net\\netprofiles\\service\\src"...
0x18002f127  mov     edx, 60h ; '`'; void *
0x18002f12c  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002f131  jmp     short loc_18002F0B6
0x18002f133  call    cs:__imp_CloseHandle
0x18002f139  jmp     loc_18002F025
0x18002f13e  call    cs:__imp_CloseHandle
0x18002f144  jmp     loc_18002F07F
0x18002f149  xor     al, al
0x18002f14b  jmp     loc_18002EF4D
```
