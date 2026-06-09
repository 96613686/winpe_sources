# Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)

- ea: `0x18000d9e8`
- end: `0x18000db16`
- name: `?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE IfSpec)`
- caller_count: `19`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007610`
- `0x180007d00`
- `0x180008850`
- `0x180008c90`
- `0x180009a94`
- `0x18000aba0`
- `0x18000bb80`
- `0x18000bdf0`
- `0x18000bfa0`
- `0x18000c080`
- `0x18000c270`
- `0x18000c720`
- `0x18000c850`
- `0x18000c9e0`
- `0x18000cac0`
- `0x18000d010`
- `0x18000d390`
- `0x18000d4f0`
- `0x18000d6d0`

## callees

- `0x180001550`
- `0x18000672c`
- `0x18000d9e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dab3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dab3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dacb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dacb`
- `RPCRT4!RpcBindingFree` at `0x18000da7a`
- `RPCRT4!RpcBindingFree` at `0x18000dac3`
- `RPCRT4!RpcBindingFree` at `0x18000daed`
- `RPCRT4!RpcBindingFree` at `0x18000da7a`
- `RPCRT4!RpcBindingFree` at `0x18000dac3`
- `RPCRT4!RpcBindingFree` at `0x18000daed`
- `RPCRT4!RpcBindingBind` at `0x18000da8d`
- `RPCRT4!RpcBindingBind` at `0x18000da8d`
- `RPCRT4!RpcBindingCreateW` at `0x18000da45`
- `RPCRT4!RpcBindingCreateW` at `0x18000da45`

## string_xrefs

- `0x18000da58`: `onecore\base\gendrv\silos\clem\rpc\common\rpcutilities.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::ConnectToServer(RPC_IF_HANDLE IfSpec, RPC_BINDING_HANDLE *a2)
{
  unsigned int v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // ebx
  RPC_BINDING_HANDLE v8; // rsi
  RPC_BINDING_HANDLE v9; // r14
  DWORD LastError; // eax
  DWORD v11; // ebx
  RPC_BINDING_HANDLE v12; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-50h] BYREF
  RPC_BINDING_HANDLE v14; // [rsp+28h] [rbp-48h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+30h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  memset(&Template, 0, sizeof(Template));
  Template.Version = 1;
  Template.ProtocolSequence = 3;
  Binding = 0;
  v4 = RpcBindingCreateW(&Template, 0, 0, &Binding);
  if ( v4 )
  {
    v5 = 153;
LABEL_3:
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v5,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\rpcutilities.cpp",
           (const char *)v4,
           (unsigned int)Binding);
    if ( Binding )
    {
      v14 = Binding;
      RpcBindingFree(&v14);
    }
    return v6;
  }
  v4 = RpcBindingBind(0, Binding, IfSpec);
  if ( v4 )
  {
    v5 = 157;
    goto LABEL_3;
  }
  if ( a2 == &Binding )
  {
    v12 = Binding;
  }
  else
  {
    v8 = *a2;
    v9 = Binding;
    if ( *a2 )
    {
      LastError = GetLastError();
      v14 = v8;
      v11 = LastError;
      RpcBindingFree(&v14);
      SetLastError(v11);
    }
    v12 = 0;
    *a2 = v9;
    Binding = 0;
  }
  if ( v12 )
  {
    v14 = v12;
    RpcBindingFree(&v14);
  }
  return 0;
}

```

## disassembly

```asm
0x18000d9e8  mov     [rsp-18h+arg_10], rbx
0x18000d9ed  mov     [rsp-18h+arg_18], rsi
0x18000d9f2  push    rbp
0x18000d9f3  push    rdi
0x18000d9f4  push    r14
0x18000d9f6  mov     rbp, rsp
0x18000d9f9  sub     rsp, 70h
0x18000d9fd  mov     rax, cs:__security_cookie
0x18000da04  xor     rax, rsp
0x18000da07  mov     [rbp+var_8], rax
0x18000da0b  xorps   xmm0, xmm0
0x18000da0e  lea     r9, [rbp+Binding]; Binding
0x18000da12  xor     eax, eax
0x18000da14  mov     rdi, rdx
0x18000da17  movups  xmmword ptr [rbp+Template.Version], xmm0
0x18000da1b  mov     rbx, rcx
0x18000da1e  mov     [rbp+Template.Version], 1
0x18000da25  xor     r8d, r8d; Options
0x18000da28  mov     [rbp+Template.ProtocolSequence], 3
0x18000da2f  xor     edx, edx; Security
0x18000da31  mov     qword ptr [rbp+Template.ObjectUuid.Data4], rax
0x18000da35  lea     rcx, [rbp+Template]; Template
0x18000da39  mov     [rbp+Binding], rax
0x18000da3d  movups  xmmword ptr [rbp+Template.NetworkAddress], xmm0
0x18000da41  movups  xmmword ptr [rbp+Template.u1], xmm0
0x18000da45  call    cs:__imp_RpcBindingCreateW
0x18000da4b  test    eax, eax
0x18000da4d  jz      short loc_18000DA84
0x18000da4f  mov     edx, 99h; void *
0x18000da54  mov     rcx, [rbp+18h]; this
0x18000da58  lea     r8, aOnecoreBaseGen_9; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000da5f  mov     r9d, eax; char *
0x18000da62  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000da67  mov     rcx, [rbp+Binding]
0x18000da6b  mov     ebx, eax
0x18000da6d  test    rcx, rcx
0x18000da70  jz      short loc_18000DA80
0x18000da72  mov     [rbp+var_48], rcx
0x18000da76  lea     rcx, [rbp+var_48]; Binding
0x18000da7a  call    cs:__imp_RpcBindingFree
0x18000da80  mov     eax, ebx
0x18000da82  jmp     short loc_18000DAF5
0x18000da84  mov     rdx, [rbp+Binding]; Binding
0x18000da88  mov     r8, rbx; IfSpec
0x18000da8b  xor     ecx, ecx; pAsync
0x18000da8d  call    cs:__imp_RpcBindingBind
0x18000da93  test    eax, eax
0x18000da95  jz      short loc_18000DA9E
0x18000da97  mov     edx, 9Dh
0x18000da9c  jmp     short loc_18000DA54
0x18000da9e  lea     rax, [rbp+Binding]
0x18000daa2  cmp     rdi, rax
0x18000daa5  jz      short loc_18000DADC
0x18000daa7  mov     rsi, [rdi]
0x18000daaa  mov     r14, [rbp+Binding]
0x18000daae  test    rsi, rsi
0x18000dab1  jz      short loc_18000DAD1
0x18000dab3  call    cs:__imp_GetLastError
0x18000dab9  lea     rcx, [rbp+var_48]; Binding
0x18000dabd  mov     [rbp+var_48], rsi
0x18000dac1  mov     ebx, eax
0x18000dac3  call    cs:__imp_RpcBindingFree
0x18000dac9  mov     ecx, ebx; dwErrCode
0x18000dacb  call    cs:__imp_SetLastError
0x18000dad1  xor     eax, eax
0x18000dad3  mov     [rdi], r14
0x18000dad6  mov     [rbp+Binding], rax
0x18000dada  jmp     short loc_18000DAE0
0x18000dadc  mov     rax, [rbp+Binding]
0x18000dae0  test    rax, rax
0x18000dae3  jz      short loc_18000DAF3
0x18000dae5  lea     rcx, [rbp+var_48]; Binding
0x18000dae9  mov     [rbp+var_48], rax
0x18000daed  call    cs:__imp_RpcBindingFree
0x18000daf3  xor     eax, eax
0x18000daf5  mov     rcx, [rbp+var_8]
0x18000daf9  xor     rcx, rsp; StackCookie
0x18000dafc  call    __security_check_cookie
0x18000db01  lea     r11, [rsp+70h+var_s0]
0x18000db06  mov     rbx, [r11+30h]
0x18000db0a  mov     rsi, [r11+38h]
0x18000db0e  mov     rsp, r11
0x18000db11  pop     r14
0x18000db13  pop     rdi
0x18000db14  pop     rbp
0x18000db15  retn
```
