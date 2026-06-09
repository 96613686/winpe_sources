# IsRpcAccessAllowed(void)

- ea: `0x180030e34`
- end: `0x18003100a`
- name: `?IsRpcAccessAllowed@@YA@XZ`
- size: `470`
- prototype: `char(void)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800658c0`
- `0x1801091c0`
- `0x180109500`

## callees

- `0x180020d20`
- `0x1800307cc`
- `0x180030e34`
- `0x1800327c0`
- `0x1800713b8`
- `0x1800a88a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180030e82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180030e82`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180030e9a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180030e9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030fe2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030fe2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180030f95`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180030f9d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180030f95`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180030f9d`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180030f06`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180030f06`
- `RPCRT4!RpcRevertToSelfEx` at `0x180030f33`
- `RPCRT4!RpcRevertToSelfEx` at `0x180030fb3`
- `RPCRT4!RpcRevertToSelfEx` at `0x180030f33`
- `RPCRT4!RpcRevertToSelfEx` at `0x180030fb3`
- `RPCRT4!RpcImpersonateClient` at `0x180030e51`
- `RPCRT4!RpcImpersonateClient` at `0x180030e51`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180030ee9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180030ee9`

## string_xrefs

- `0x180030e64`: `onecore\net\netprofiles\service\src\l2manager\lib\pluginserver.cpp`
- `0x180030f41`: `onecore\net\netprofiles\service\src\l2manager\lib\pluginserver.cpp`
- `0x180030f72`: `onecore\net\netprofiles\service\src\l2manager\lib\pluginserver.cpp`
- `0x180030fcf`: `onecore\net\netprofiles\service\src\l2manager\lib\pluginserver.cpp`
- `0x180030ff1`: `onecore\net\netprofiles\service\src\l2manager\lib\pluginserver.cpp`

## pseudocode

```c
char IsRpcAccessAllowed(void)
{
  unsigned int v0; // eax
  __int64 v1; // rdx
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  WINBOOL *v5; // rdi
  const WCHAR *v6; // rcx
  const char *v7; // r9
  unsigned int v8; // eax
  _QWORD v9[3]; // [rsp+20h] [rbp-40h] BYREF
  WINBOOL IsMember; // [rsp+38h] [rbp-28h] BYREF
  PSID Sid; // [rsp+40h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v0 = RpcImpersonateClient(0);
  if ( v0 )
  {
    v1 = 128;
    goto LABEL_3;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\lib\\pluginserver.cpp",
      v4);
LABEL_22:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    v0 = RpcRevertToSelfEx(0);
    if ( !v0 )
      return 0;
    v1 = 133;
LABEL_3:
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)v1,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\lib\\pluginserver.cpp",
      (const char *)v0,
      v9[0]);
    return 0;
  }
  v9[0] = L"S-1-5-80-4071458001-3563271761-1846288968-3700919931-3809667977";
  v5 = (WINBOOL *)v9;
  v9[1] = L"S-1-5-80-1428027539-3309602793-2678353003-1498846795-3763184142";
  v9[2] = L"S-1-5-80-3981856537-581775623-1136376035-2066872258-409572886";
  while ( 1 )
  {
    if ( v5 == &IsMember )
    {
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0xA4,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\lib\\pluginserver.cpp",
        (const char *)5,
        v9[0]);
      goto LABEL_22;
    }
    v6 = *(const WCHAR **)v5;
    Sid = 0;
    if ( !ConvertStringSidToSidW(v6, &Sid) )
    {
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x99,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\lib\\pluginserver.cpp",
        v7);
      goto LABEL_19;
    }
    IsMember = 0;
    if ( CheckTokenMembership(TokenHandle, Sid, &IsMember) )
    {
      if ( IsMember )
        break;
    }
LABEL_19:
    if ( Sid )
      FreeSid(Sid);
    v5 += 2;
  }
  if ( Sid )
    FreeSid(Sid);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  v8 = RpcRevertToSelfEx(0);
  if ( v8 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x85,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\lib\\pluginserver.cpp",
      (const char *)v8,
      v9[0]);
  return 1;
}

```

## disassembly

```asm
0x180030e34  mov     [rsp-8+arg_0], rdi
0x180030e39  push    rbp
0x180030e3a  mov     rbp, rsp
0x180030e3d  sub     rsp, 60h
0x180030e41  mov     rax, cs:__security_cookie
0x180030e48  xor     rax, rsp
0x180030e4b  mov     [rbp+var_10], rax
0x180030e4f  xor     ecx, ecx; BindingHandle
0x180030e51  call    cs:__imp_RpcImpersonateClient
0x180030e57  test    eax, eax
0x180030e59  jz      short loc_180030E7A
0x180030e5b  mov     edx, 80h; void *
0x180030e60  mov     rcx, [rbp+8]; this
0x180030e64  lea     r8, aOnecoreNetNetp_42; "onecore\\net\\netprofiles\\service\\src"...
0x180030e6b  mov     r9d, eax; char *
0x180030e6e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180030e73  xor     al, al
0x180030e75  jmp     loc_180030F57
0x180030e7a  mov     [rbp+TokenHandle], 0
0x180030e82  call    cs:__imp_GetCurrentThread
0x180030e88  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180030e8c  mov     edx, 0F01FFh; DesiredAccess
0x180030e91  mov     rcx, rax; ThreadHandle
0x180030e94  mov     r8d, 1; OpenAsSelf
0x180030e9a  call    cs:__imp_OpenThreadToken
0x180030ea0  test    eax, eax
0x180030ea2  jz      loc_180030FCB
0x180030ea8  lea     rax, aS1580407145800; "S-1-5-80-4071458001-3563271761-18462889"...
0x180030eaf  mov     [rbp+var_40], rax
0x180030eb3  lea     rdi, [rbp+var_40]
0x180030eb7  lea     rax, aS1580142802753; "S-1-5-80-1428027539-3309602793-26783530"...
0x180030ebe  mov     [rbp+var_38], rax
0x180030ec2  lea     rax, aS1580398185653; "S-1-5-80-3981856537-581775623-113637603"...
0x180030ec9  mov     [rbp+var_30], rax
0x180030ecd  lea     rax, [rbp+IsMember]
0x180030ed1  cmp     rdi, rax
0x180030ed4  jz      loc_180030FED
0x180030eda  mov     rcx, [rdi]; StringSid
0x180030edd  lea     rdx, [rbp+Sid]; Sid
0x180030ee1  mov     [rbp+Sid], 0
0x180030ee9  call    cs:__imp_ConvertStringSidToSidW
0x180030eef  test    eax, eax
0x180030ef1  jz      short loc_180030F6E
0x180030ef3  mov     rdx, [rbp+Sid]; SidToCheck
0x180030ef7  lea     r8, [rbp+IsMember]; IsMember
0x180030efb  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180030eff  mov     [rbp+IsMember], 0
0x180030f06  call    cs:__imp_CheckTokenMembership
0x180030f0c  test    eax, eax
0x180030f0e  jz      short loc_180030F83
0x180030f10  cmp     [rbp+IsMember], 0
0x180030f14  jz      short loc_180030F83
0x180030f16  mov     rcx, [rbp+Sid]; pSid
0x180030f1a  test    rcx, rcx
0x180030f1d  jnz     short loc_180030F9D
0x180030f1f  mov     rcx, [rbp+TokenHandle]; hObject
0x180030f23  lea     rax, [rcx-1]
0x180030f27  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180030f2b  jbe     loc_180030FE2
0x180030f31  xor     ecx, ecx; BindingHandle
0x180030f33  call    cs:__imp_RpcRevertToSelfEx
0x180030f39  test    eax, eax
0x180030f3b  jz      short loc_180030F55
0x180030f3d  mov     rcx, [rbp+8]; this
0x180030f41  lea     r8, aOnecoreNetNetp_42; "onecore\\net\\netprofiles\\service\\src"...
0x180030f48  mov     r9d, eax; char *
0x180030f4b  mov     edx, 85h; void *
0x180030f50  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180030f55  mov     al, 1
0x180030f57  mov     rcx, [rbp+var_10]
0x180030f5b  xor     rcx, rsp; StackCookie
0x180030f5e  call    __security_check_cookie
0x180030f63  mov     rdi, [rsp+60h+arg_0]
0x180030f68  add     rsp, 60h
0x180030f6c  pop     rbp
0x180030f6d  retn
0x180030f6e  mov     rcx, [rbp+8]; this
0x180030f72  lea     r8, aOnecoreNetNetp_42; "onecore\\net\\netprofiles\\service\\src"...
0x180030f79  mov     edx, 99h; void *
0x180030f7e  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180030f83  mov     rcx, [rbp+Sid]; pSid
0x180030f87  test    rcx, rcx
0x180030f8a  jnz     short loc_180030F95
0x180030f8c  add     rdi, 8
0x180030f90  jmp     loc_180030ECD
0x180030f95  call    cs:__imp_FreeSid
0x180030f9b  jmp     short loc_180030F8C
0x180030f9d  call    cs:__imp_FreeSid
0x180030fa3  jmp     loc_180030F1F
0x180030fa8  lea     rcx, [rbp+TokenHandle]
0x180030fac  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180030fb1  xor     ecx, ecx; BindingHandle
0x180030fb3  call    cs:__imp_RpcRevertToSelfEx
0x180030fb9  test    eax, eax
0x180030fbb  jz      loc_180030E73
0x180030fc1  mov     edx, 85h
0x180030fc6  jmp     loc_180030E60
0x180030fcb  mov     rcx, [rbp+8]; this
0x180030fcf  lea     r8, aOnecoreNetNetp_42; "onecore\\net\\netprofiles\\service\\src"...
0x180030fd6  mov     edx, 8Bh; void *
0x180030fdb  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180030fe0  jmp     short loc_180030FA8
0x180030fe2  call    cs:__imp_CloseHandle
0x180030fe8  jmp     loc_180030F31
0x180030fed  mov     rcx, [rbp+8]; this
0x180030ff1  lea     r8, aOnecoreNetNetp_42; "onecore\\net\\netprofiles\\service\\src"...
0x180030ff8  mov     r9d, 5; char *
0x180030ffe  mov     edx, 0A4h; void *
0x180031003  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180031008  jmp     short loc_180030FA8
```
