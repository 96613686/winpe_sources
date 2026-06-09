# ComputeService::Client::Details::MakeBinding(ushort const *)

- ea: `0x18002e6e0`
- end: `0x18002e80b`
- name: `?MakeBinding@Details@Client@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z`
- size: `299`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e3d4`

## callees

- `0x1800067c0`
- `0x180027380`
- `0x18002e6e0`

## import_xrefs

- `RPCRT4!RpcBindingBind` at `0x18002e7ab`
- `RPCRT4!RpcBindingBind` at `0x18002e7ab`
- `RPCRT4!RpcBindingCreateW` at `0x18002e795`
- `RPCRT4!RpcBindingCreateW` at `0x18002e795`

## string_xrefs

- `0x18002e7e0`: `onecore\vm\compute\dll\lib\core\rpcclient.cpp`
- `0x18002e7f9`: `onecore\vm\compute\dll\lib\core\rpcclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
RPC_BINDING_HANDLE *__fastcall ComputeService::Client::Details::MakeBinding(
        RPC_BINDING_HANDLE *Binding,
        unsigned __int16 *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // eax
  __int64 v6; // [rsp+30h] [rbp-49h] BYREF
  int v7; // [rsp+38h] [rbp-41h]
  __int64 v8; // [rsp+3Ch] [rbp-3Dh]
  __int64 v9; // [rsp+44h] [rbp-35h]
  int v10; // [rsp+4Ch] [rbp-2Dh]
  __int64 v11; // [rsp+50h] [rbp-29h]
  int v12; // [rsp+58h] [rbp-21h]
  __int64 v13; // [rsp+5Ch] [rbp-1Dh]
  int v14; // [rsp+64h] [rbp-15h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+68h] [rbp-11h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *(&Template.ProtocolSequence + 1) = 0;
  Template.NetworkAddress = 0;
  memset(&Template.u1, 0, 24);
  *(_QWORD *)&Security.Version = 1;
  Security.AuthIdentity = 0;
  v9 = 0;
  v10 = 0;
  v13 = 0;
  v14 = 0;
  *(_QWORD *)&Template.Version = 1;
  Template.ProtocolSequence = 3;
  Template.StringEndpoint = a2;
  Security.ServerPrincName = 0;
  Security.AuthnLevel = 5;
  Security.AuthnSvc = 10;
  Security.SecurityQos = (RPC_SECURITY_QOS *)&v6;
  v6 = 5;
  v7 = 1;
  v8 = 3;
  v11 = 0;
  v12 = 0;
  *Binding = 0;
  v3 = RpcBindingCreateW(&Template, &Security, 0, Binding);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\rpcclient.cpp",
      (const char *)v3,
      1u);
  v4 = RpcBindingBind(0, *Binding, qword_1800AA120);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\rpcclient.cpp",
      (const char *)v4,
      1u);
  return Binding;
}

```

## disassembly

```asm
0x18002e6e0  mov     [rsp-8+arg_10], rbx
0x18002e6e5  mov     [rsp-8+arg_18], rdi
0x18002e6ea  push    rbp
0x18002e6eb  lea     rbp, [rsp-57h]
0x18002e6f0  sub     rsp, 0D0h
0x18002e6f7  mov     rax, cs:__security_cookie
0x18002e6fe  xor     rax, rsp
0x18002e701  mov     [rbp+57h+var_8], rax
0x18002e705  mov     rbx, rcx
0x18002e708  mov     [rbp+57h+var_A8], rcx
0x18002e70c  xor     edi, edi
0x18002e70e  mov     [rbp+57h+var_B0], edi
0x18002e711  xorps   xmm0, xmm0
0x18002e714  xor     eax, eax
0x18002e716  movups  xmmword ptr [rbp+57h+Template.Version], xmm0
0x18002e71a  movups  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x18002e71e  movups  xmmword ptr [rbp+57h+Template.u1], xmm0
0x18002e722  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data4], rax
0x18002e726  mov     qword ptr [rbp+57h+Security.Version], 1
0x18002e72e  mov     [rbp+57h+Security.AuthIdentity], rdi
0x18002e732  mov     [rbp+57h+var_8C], rdi
0x18002e736  mov     [rbp+57h+var_84], edi
0x18002e739  mov     [rbp+57h+var_74], rdi
0x18002e73d  mov     [rbp+57h+var_6C], edi
0x18002e740  lea     r9d, [rdi+1]
0x18002e744  mov     qword ptr [rbp+57h+Template.Version], r9
0x18002e748  lea     r8d, [rdi+3]
0x18002e74c  mov     [rbp+57h+Template.ProtocolSequence], r8d
0x18002e750  mov     [rbp+57h+Template.StringEndpoint], rdx
0x18002e754  mov     [rbp+57h+Security.ServerPrincName], rdi
0x18002e758  lea     ecx, [rdi+5]
0x18002e75b  mov     [rbp+57h+Security.AuthnLevel], ecx
0x18002e75e  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x18002e765  lea     rax, [rbp+57h+var_A0]
0x18002e769  mov     [rbp+57h+Security.SecurityQos], rax
0x18002e76d  mov     [rbp+57h+var_A0], rcx
0x18002e771  mov     [rbp+57h+var_98], r9d
0x18002e775  mov     [rbp+57h+var_94], r8
0x18002e779  mov     [rbp+57h+var_80], rdi
0x18002e77d  mov     [rbp+57h+var_78], edi
0x18002e780  mov     [rbp+57h+var_B0], r9d
0x18002e784  mov     [rbx], rdi
0x18002e787  mov     r9, rbx; Binding
0x18002e78a  xor     r8d, r8d; Options
0x18002e78d  lea     rdx, [rbp+57h+Security]; Security
0x18002e791  lea     rcx, [rbp+57h+Template]; Template
0x18002e795  call    cs:__imp_RpcBindingCreateW
0x18002e79b  test    eax, eax
0x18002e79d  jnz     short loc_18002E7F2
0x18002e79f  lea     r8, qword_1800AA120; IfSpec
0x18002e7a6  mov     rdx, [rbx]; Binding
0x18002e7a9  xor     ecx, ecx; pAsync
0x18002e7ab  call    cs:__imp_RpcBindingBind
0x18002e7b1  test    eax, eax
0x18002e7b3  jnz     short loc_18002E7D9
0x18002e7b5  mov     rax, rbx
0x18002e7b8  mov     rcx, [rbp+57h+var_8]
0x18002e7bc  xor     rcx, rsp; StackCookie
0x18002e7bf  call    __security_check_cookie
0x18002e7c4  lea     r11, [rsp+0D0h+var_s0]
0x18002e7cc  mov     rbx, [r11+20h]
0x18002e7d0  mov     rdi, [r11+28h]
0x18002e7d4  mov     rsp, r11
0x18002e7d7  pop     rbp
0x18002e7d8  retn
0x18002e7d9  mov     rcx, [rbp+5Fh]; this
0x18002e7dd  mov     r9d, eax; char *
0x18002e7e0  lea     r8, aOnecoreVmCompu_6; "onecore\\vm\\compute\\dll\\lib\\core\\r"...
0x18002e7e7  mov     edx, 47h ; 'G'; void *
0x18002e7ec  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002e7f2  mov     rcx, [rbp+5Fh]; this
0x18002e7f6  mov     r9d, eax; char *
0x18002e7f9  lea     r8, aOnecoreVmCompu_6; "onecore\\vm\\compute\\dll\\lib\\core\\r"...
0x18002e800  mov     edx, 45h ; 'E'; void *
0x18002e805  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
