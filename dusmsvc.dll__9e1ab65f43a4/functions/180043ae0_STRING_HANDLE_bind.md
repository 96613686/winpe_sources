# STRING_HANDLE_bind

- ea: `0x180043ae0`
- end: `0x180043cf7`
- name: `STRING_HANDLE_bind`
- size: `535`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007c90`
- `0x1800172c8`
- `0x180043ae0`
- `0x180043f48`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180043c36`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180043c36`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x180043bed`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x180043bed`
- `RPCRT4!RpcBindingSetOption` at `0x180043bbd`
- `RPCRT4!RpcBindingSetOption` at `0x180043bbd`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180043b7d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180043b7d`
- `RPCRT4!RpcStringBindingComposeW` at `0x180043b45`
- `RPCRT4!RpcStringBindingComposeW` at `0x180043b45`
- `RPCRT4!RpcStringFreeW` at `0x180043c56`
- `RPCRT4!RpcStringFreeW` at `0x180043c6a`
- `RPCRT4!RpcStringFreeW` at `0x180043c56`
- `RPCRT4!RpcStringFreeW` at `0x180043c6a`

## string_xrefs

- `0x180043b26`: `Security=Impersonation Dynamic False`
- `0x180043c93`: `onecore\net\netprofiles\service\src\l2manager\clientlib\rpcbinding.cpp`
- `0x180043ca8`: `onecore\net\netprofiles\service\src\l2manager\clientlib\rpcbinding.cpp`
- `0x180043cbd`: `onecore\net\netprofiles\service\src\l2manager\clientlib\rpcbinding.cpp`
- `0x180043cd1`: `onecore\net\netprofiles\service\src\l2manager\clientlib\rpcbinding.cpp`
- `0x180043ce4`: `onecore\net\netprofiles\service\src\l2manager\clientlib\rpcbinding.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
RPC_BINDING_HANDLE __fastcall STRING_HANDLE_bind(RPC_WSTR NetworkAddr)
{
  unsigned int v1; // eax
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  RPC_BINDING_HANDLE v6; // rbx
  const char *v7; // r9
  RPC_BINDING_HANDLE result; // rax
  unsigned int Options; // [rsp+20h] [rbp-78h]
  unsigned int Optionsa; // [rsp+20h] [rbp-78h]
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp-30h] BYREF
  RPC_WSTR String; // [rsp+70h] [rbp-28h] BYREF
  RPC_WSTR ServerPrincName; // [rsp+78h] [rbp-20h] BYREF
  unsigned __int16 *v14; // [rsp+80h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  try
  {
    v14 = NetworkAddr;
    if ( NetworkAddr )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(NetworkAddr);
      NetworkAddr = v14;
    }
    String = 0;
    v1 = RpcStringBindingComposeW(
           0,
           (RPC_WSTR)L"ncalrpc",
           NetworkAddr,
           (RPC_WSTR)L"nlaplg",
           (RPC_WSTR)L"Security=Impersonation Dynamic False",
           &String);
    if ( v1 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x15,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\rpcbinding.cpp",
        (const char *)v1,
        Options);
    Binding = 0;
    v2 = RpcBindingFromStringBindingW(String, &Binding);
    if ( v2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1F,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\rpcbinding.cpp",
        (const char *)v2,
        Options);
    v3 = RpcBindingSetOption(Binding, 0xBu, 1u);
    if ( v3 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x25,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\rpcbinding.cpp",
        (const char *)v3,
        Options);
    ServerPrincName = 0;
    v4 = RpcMgmtInqServerPrincNameW(Binding, 0xAu, &ServerPrincName);
    if ( v4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\rpcbinding.cpp",
        (const char *)v4,
        Options);
    v5 = RpcBindingSetAuthInfoW(Binding, ServerPrincName, 6u, 0xAu, 0, 0);
    if ( v5 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\rpcbinding.cpp",
        (const char *)v5,
        Optionsa);
    v6 = Binding;
    RpcStringFreeW(&ServerPrincName);
    if ( String )
      RpcStringFreeW(&String);
    result = v6;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\rpcbinding.cpp",
      v7);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180043ae0  mov     r11, rsp
0x180043ae3  push    rbx
0x180043ae4  sub     rsp, 90h
0x180043aeb  mov     rax, cs:__security_cookie
0x180043af2  xor     rax, rsp
0x180043af5  mov     [rsp+98h+var_10], rax
0x180043afd  mov     [r11-18h], rcx
0x180043b01  test    rcx, rcx
0x180043b04  jz      short loc_180043B13
0x180043b06  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180043b0b  mov     rcx, [rsp+98h+var_18]
0x180043b13  mov     [rsp+98h+String], 0
0x180043b1c  lea     rax, [rsp+98h+String]
0x180043b21  mov     [rsp+98h+StringBinding], rax; StringBinding
0x180043b26  lea     rax, Options; "Security=Impersonation Dynamic False"
0x180043b2d  mov     [rsp+98h+Options], rax; unsigned int
0x180043b32  lea     r9, Endpoint; "nlaplg"
0x180043b39  mov     r8, rcx; NetworkAddr
0x180043b3c  lea     rdx, ProtSeq; "ncalrpc"
0x180043b43  xor     ecx, ecx; ObjUuid
0x180043b45  call    cs:__imp_RpcStringBindingComposeW
0x180043b4b  mov     rcx, [rsp+98h]; this
0x180043b53  test    eax, eax
0x180043b55  jnz     loc_180043C90
0x180043b5b  lea     rax, [rsp+98h+String]
0x180043b60  mov     [rsp+98h+var_68], rax
0x180043b65  mov     [rsp+98h+var_60], 1
0x180043b6a  mov     [rsp+98h+Binding], 0
0x180043b73  lea     rdx, [rsp+98h+Binding]; Binding
0x180043b78  mov     rcx, [rsp+98h+String]; StringBinding
0x180043b7d  call    cs:__imp_RpcBindingFromStringBindingW
0x180043b83  mov     rcx, [rsp+98h]; this
0x180043b8b  test    eax, eax
0x180043b8d  jnz     loc_180043CA5
0x180043b93  lea     rax, [rsp+98h+var_18]
0x180043b9b  mov     [rsp+98h+var_48], rax
0x180043ba0  lea     rax, [rsp+98h+Binding]
0x180043ba5  mov     [rsp+98h+var_40], rax
0x180043baa  mov     [rsp+98h+var_38], 1
0x180043baf  mov     edx, 0Bh; option
0x180043bb4  lea     r8d, [rdx-0Ah]; optionValue
0x180043bb8  mov     rcx, [rsp+98h+Binding]; hBinding
0x180043bbd  call    cs:__imp_RpcBindingSetOption
0x180043bc3  mov     rcx, [rsp+98h]; this
0x180043bcb  test    eax, eax
0x180043bcd  jnz     loc_180043CBA
0x180043bd3  mov     [rsp+98h+ServerPrincName], 0
0x180043bdc  lea     r8, [rsp+98h+ServerPrincName]; ServerPrincName
0x180043be1  mov     ebx, 0Ah
0x180043be6  mov     edx, ebx; AuthnSvc
0x180043be8  mov     rcx, [rsp+98h+Binding]; Binding
0x180043bed  call    cs:__imp_RpcMgmtInqServerPrincNameW
0x180043bf3  mov     rcx, [rsp+98h]; this
0x180043bfb  test    eax, eax
0x180043bfd  jnz     loc_180043CCE
0x180043c03  lea     rax, [rsp+98h+ServerPrincName]
0x180043c08  mov     [rsp+98h+var_58], rax
0x180043c0d  mov     [rsp+98h+var_50], 1
0x180043c12  mov     dword ptr [rsp+98h+StringBinding], 0; AuthzSvc
0x180043c1a  mov     [rsp+98h+Options], 0; unsigned int
0x180043c23  mov     r9d, ebx; AuthnSvc
0x180043c26  mov     r8d, 6; AuthnLevel
0x180043c2c  mov     rdx, [rsp+98h+ServerPrincName]; ServerPrincName
0x180043c31  mov     rcx, [rsp+98h+Binding]; Binding
0x180043c36  call    cs:__imp_RpcBindingSetAuthInfoW
0x180043c3c  mov     rcx, [rsp+98h]; this
0x180043c44  test    eax, eax
0x180043c46  jnz     loc_180043CE1
0x180043c4c  mov     rbx, [rsp+98h+Binding]
0x180043c51  lea     rcx, [rsp+98h+ServerPrincName]; String
0x180043c56  call    cs:__imp_RpcStringFreeW
0x180043c5c  nop
0x180043c5d  cmp     [rsp+98h+String], 0
0x180043c63  jz      short loc_180043C70
0x180043c65  lea     rcx, [rsp+98h+String]; String
0x180043c6a  call    cs:__imp_RpcStringFreeW
0x180043c70  mov     rax, rbx
0x180043c73  jmp     short loc_180043C77
0x180043c75  xor     eax, eax
0x180043c77  mov     rcx, [rsp+98h+var_10]
0x180043c7f  xor     rcx, rsp; StackCookie
0x180043c82  call    __security_check_cookie
0x180043c87  add     rsp, 90h
0x180043c8e  pop     rbx
0x180043c8f  retn
0x180043c90  mov     r9d, eax; char *
0x180043c93  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x180043c9a  mov     edx, 15h; void *
0x180043c9f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180043ca5  mov     r9d, eax; char *
0x180043ca8  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x180043caf  mov     edx, 1Fh; void *
0x180043cb4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180043cba  mov     r9d, eax; char *
0x180043cbd  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x180043cc4  mov     edx, 25h ; '%'; void *
0x180043cc9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180043cce  mov     r9d, eax; char *
0x180043cd1  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x180043cd8  lea     edx, [rbx+1Fh]; void *
0x180043cdb  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180043ce1  mov     r9d, eax; char *
0x180043ce4  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x180043ceb  mov     edx, 2Fh ; '/'; void *
0x180043cf0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
