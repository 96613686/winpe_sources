# Microsoft::Diagnostics::ApiServer::CheckRpcCallerIsDeviceOwner(void)

- ea: `0x1802f2074`
- end: `0x1802f21d3`
- name: `?CheckRpcCallerIsDeviceOwner@ApiServer@Diagnostics@Microsoft@@IEAAJXZ`
- size: `351`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::ApiServer *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801eb220`

## callees

- `0x180064e6c`
- `0x180064e8c`
- `0x1801bbc78`
- `0x1802f1e20`
- `0x1802f2074`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1802f2114`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1802f2114`
- `RPCRT4!RpcImpersonateClient` at `0x1802f2083`
- `RPCRT4!RpcImpersonateClient` at `0x1802f2083`
- `RPCRT4!RpcRevertToSelf` at `0x1802f20e0`
- `RPCRT4!RpcRevertToSelf` at `0x1802f2136`
- `RPCRT4!RpcRevertToSelf` at `0x1802f2180`
- `RPCRT4!RpcRevertToSelf` at `0x1802f21a5`
- `RPCRT4!RpcRevertToSelf` at `0x1802f20e0`
- `RPCRT4!RpcRevertToSelf` at `0x1802f2136`
- `RPCRT4!RpcRevertToSelf` at `0x1802f2180`
- `RPCRT4!RpcRevertToSelf` at `0x1802f21a5`

## string_xrefs

- `0x1802f2092`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f20cc`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f20ef`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f2123`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f2149`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f2167`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f2193`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f21b4`: `onecore\base\telemetry\utc\common\apiserver.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::ApiServer::CheckRpcCallerIsDeviceOwner(
        Microsoft::Diagnostics::ApiServer *this)
{
  unsigned int LastError; // ebx
  int DeviceOwnerSid; // eax
  const char *v5; // r9
  void *v6; // rdx
  const char *v7; // r9
  const char *v8; // r9
  const char *v9; // r9
  const char *v10; // r9
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  WINBOOL IsMember; // [rsp+38h] [rbp+10h] BYREF

  if ( RpcImpersonateClient(0) )
  {
    LastError = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xED,
      (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
      (const char *)0x80070005LL,
      v11);
    return LastError;
  }
  if ( !*((_QWORD *)this + 2) )
  {
    DeviceOwnerSid = Microsoft::Diagnostics::ApiServer::AllocateDeviceOwnerSid(this);
    LastError = DeviceOwnerSid;
    if ( DeviceOwnerSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFF,
        (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
        (const char *)(unsigned int)DeviceOwnerSid,
        v11);
      if ( RpcRevertToSelf() )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xF8,
          (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
          v5);
      return LastError;
    }
  }
  v6 = (void *)*((_QWORD *)this + 2);
  IsMember = 0;
  if ( !CheckTokenMembership(0, v6, &IsMember) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x103,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
                  v7);
    if ( RpcRevertToSelf() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF8,
        (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
        v8);
    return LastError;
  }
  if ( !IsMember )
  {
    LastError = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x106,
      (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
      (const char *)0x80070005LL,
      v11);
    if ( RpcRevertToSelf() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF8,
        (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
        v9);
    return LastError;
  }
  if ( RpcRevertToSelf() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
      v10);
  return 0;
}

```

## disassembly

```asm
0x1802f2074  mov     [rsp+arg_0], rbx
0x1802f2079  push    rdi; int
0x1802f207a  sub     rsp, 20h
0x1802f207e  mov     rdi, rcx
0x1802f2081  xor     ecx, ecx; BindingHandle
0x1802f2083  call    cs:__imp_RpcImpersonateClient
0x1802f2089  test    eax, eax
0x1802f208b  jz      short loc_1802F20B2
0x1802f208d  mov     rcx, [rsp+28h]; this
0x1802f2092  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f2099  mov     ebx, 80070005h
0x1802f209e  mov     edx, 0EDh; void *
0x1802f20a3  mov     r9d, ebx; char *
0x1802f20a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802f20ab  mov     eax, ebx
0x1802f20ad  jmp     loc_1802F21C8
0x1802f20b2  cmp     qword ptr [rdi+10h], 0
0x1802f20b7  jnz     short loc_1802F2101
0x1802f20b9  mov     rcx, rdi; this
0x1802f20bc  call    ?AllocateDeviceOwnerSid@ApiServer@Diagnostics@Microsoft@@IEAAJXZ; Microsoft::Diagnostics::ApiServer::AllocateDeviceOwnerSid(void)
0x1802f20c1  mov     ebx, eax
0x1802f20c3  test    eax, eax
0x1802f20c5  jns     short loc_1802F2101
0x1802f20c7  mov     rcx, [rsp+28h]; this
0x1802f20cc  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f20d3  mov     r9d, eax; char *
0x1802f20d6  mov     edx, 0FFh; void *
0x1802f20db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802f20e0  call    cs:__imp_RpcRevertToSelf
0x1802f20e6  test    eax, eax
0x1802f20e8  jz      short loc_1802F20AB
0x1802f20ea  mov     rcx, [rsp+28h]; this
0x1802f20ef  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f20f6  mov     edx, 0F8h; void *
0x1802f20fb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802f2101  mov     rdx, [rdi+10h]; SidToCheck
0x1802f2105  lea     r8, [rsp+28h+IsMember]; IsMember
0x1802f210a  xor     ecx, ecx; TokenHandle
0x1802f210c  mov     [rsp+28h+IsMember], 0
0x1802f2114  call    cs:__imp_CheckTokenMembership
0x1802f211a  test    eax, eax
0x1802f211c  jnz     short loc_1802F215B
0x1802f211e  mov     rcx, [rsp+28h]; this
0x1802f2123  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f212a  mov     edx, 103h; void *
0x1802f212f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1802f2134  mov     ebx, eax
0x1802f2136  call    cs:__imp_RpcRevertToSelf
0x1802f213c  test    eax, eax
0x1802f213e  jz      loc_1802F20AB
0x1802f2144  mov     rcx, [rsp+28h]; this
0x1802f2149  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f2150  mov     edx, 0F8h; void *
0x1802f2155  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802f215b  cmp     [rsp+28h+IsMember], 0
0x1802f2160  jnz     short loc_1802F21A5
0x1802f2162  mov     rcx, [rsp+28h]; this
0x1802f2167  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f216e  mov     ebx, 80070005h
0x1802f2173  mov     edx, 106h; void *
0x1802f2178  mov     r9d, ebx; char *
0x1802f217b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802f2180  call    cs:__imp_RpcRevertToSelf
0x1802f2186  test    eax, eax
0x1802f2188  jz      loc_1802F20AB
0x1802f218e  mov     rcx, [rsp+28h]; this
0x1802f2193  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f219a  mov     edx, 0F8h; void *
0x1802f219f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802f21a5  call    cs:__imp_RpcRevertToSelf
0x1802f21ab  test    eax, eax
0x1802f21ad  jz      short loc_1802F21C6
0x1802f21af  mov     rcx, [rsp+28h]; this
0x1802f21b4  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f21bb  mov     edx, 0F8h; void *
0x1802f21c0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802f21c6  xor     eax, eax
0x1802f21c8  mov     rbx, [rsp+28h+arg_0]
0x1802f21cd  add     rsp, 20h
0x1802f21d1  pop     rdi
0x1802f21d2  retn
```
