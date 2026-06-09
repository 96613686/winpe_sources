# Rpc::RpcClient::CreateIdentifyableLrpcBindingHandle(void)

- ea: `0x18000bef4`
- end: `0x18000c084`
- name: `?CreateIdentifyableLrpcBindingHandle@RpcClient@Rpc@@AEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `400`
- prototype: `RPC_BINDING_HANDLE *__fastcall(__int64, RPC_BINDING_HANDLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bd5c`

## callees

- `0x180001600`
- `0x180007904`
- `0x18000bef4`
- `0x18000c0bc`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x18000c003`
- `RPCRT4!RpcBindingCreateW` at `0x18000c003`
- `RPCRT4!UuidFromStringW` at `0x18000bf8d`
- `RPCRT4!UuidFromStringW` at `0x18000bf8d`
- `RPCRT4!RpcBindingBind` at `0x18000c019`
- `RPCRT4!RpcBindingBind` at `0x18000c019`

## string_xrefs

- `0x18000c05d`: `onecore\vm\dv\net\hns\service\common\rpc\client\rpcclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
RPC_BINDING_HANDLE *__fastcall Rpc::RpcClient::CreateIdentifyableLrpcBindingHandle(__int64 a1, RPC_BINDING_HANDLE *a2)
{
  unsigned __int16 *v4; // rcx
  unsigned int v5; // eax
  unsigned int v6; // r8d
  unsigned int v7; // eax
  unsigned int v8; // r8d
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+28h] [rbp-61h] BYREF
  _OWORD v11[2]; // [rsp+50h] [rbp-39h] BYREF
  __int128 v12; // [rsp+70h] [rbp-19h]
  __int64 v13; // [rsp+80h] [rbp-9h]
  RPC_BINDING_HANDLE *v14; // [rsp+88h] [rbp-1h]
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v14 = a2;
  memset(&Template.ProtocolSequence + 1, 0, 44);
  memset(&Security, 0, sizeof(Security));
  memset(v11, 0, sizeof(v11));
  v12 = 0;
  v13 = 0;
  *(_QWORD *)&Template.Version = 1;
  Template.ProtocolSequence = 3;
  if ( *(_QWORD *)(a1 + 128) )
  {
    v4 = (unsigned __int16 *)(a1 + 112);
    if ( *((_QWORD *)v4 + 3) > 7u )
      v4 = *(unsigned __int16 **)v4;
    if ( UuidFromStringW(v4, &Template.ObjectUuid) )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\rpc\\client\\rpcclient.cpp",
        (const char *)0x803B0019LL,
        0);
    Template.Flags |= 1u;
  }
  Security.Version = 1;
  Security.ServerPrincName = 0;
  Security.AuthnLevel = 5;
  Security.AuthnSvc = 10;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v11;
  *(_QWORD *)&v11[0] = 5;
  DWORD2(v11[0]) = 1;
  *(_QWORD *)((char *)v11 + 12) = 2;
  *(_QWORD *)&v12 = 0;
  DWORD2(v12) = 0;
  *a2 = 0;
  v5 = RpcBindingCreateW(&Template, &Security, 0, a2);
  if ( v5 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x6C, v6, (const char *)v5, 1u);
  v7 = RpcBindingBind(0, *a2, *(RPC_IF_HANDLE *)(a1 + 144));
  if ( v7 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x6F, v8, (const char *)v7, 1u);
  return a2;
}

```

## disassembly

```asm
0x18000bef4  mov     [rsp-8+arg_10], rbx
0x18000bef9  push    rbp
0x18000befa  push    rsi
0x18000befb  push    rdi
0x18000befc  lea     rbp, [rsp-47h]
0x18000bf01  sub     rsp, 0D0h
0x18000bf08  mov     rax, cs:__security_cookie
0x18000bf0f  xor     rax, rsp
0x18000bf12  mov     [rbp+57h+var_18], rax
0x18000bf16  mov     rbx, rdx
0x18000bf19  mov     rdi, rcx
0x18000bf1c  mov     [rbp+57h+var_58], rdx
0x18000bf20  mov     [rbp+57h+var_C0], 0
0x18000bf27  xorps   xmm0, xmm0
0x18000bf2a  xor     eax, eax
0x18000bf2c  movups  xmmword ptr [rbp+57h+Template.Version], xmm0
0x18000bf30  movups  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x18000bf34  movups  xmmword ptr [rbp+57h+Template.u1], xmm0
0x18000bf38  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data4], rax
0x18000bf3c  movups  xmmword ptr [rbp+57h+Security.Version], xmm0
0x18000bf40  movups  xmmword ptr [rbp+57h+Security.AuthnLevel], xmm0
0x18000bf44  mov     [rbp+57h+Security.SecurityQos], rax
0x18000bf48  xorps   xmm1, xmm1
0x18000bf4b  movups  [rbp+57h+var_90], xmm1
0x18000bf4f  movups  [rbp+57h+var_80], xmm1
0x18000bf53  movups  [rbp+57h+var_70], xmm1
0x18000bf57  mov     [rbp+57h+var_60], rax
0x18000bf5b  mov     qword ptr [rbp+57h+Template.Version], 1
0x18000bf63  mov     [rbp+57h+Template.ProtocolSequence], 3
0x18000bf6a  mov     [rbp+57h+Template.StringEndpoint], rax
0x18000bf6e  cmp     [rcx+80h], rax
0x18000bf75  jz      short loc_18000BF9F
0x18000bf77  add     rcx, 70h ; 'p'
0x18000bf7b  cmp     qword ptr [rcx+18h], 7
0x18000bf80  jbe     short loc_18000BF85
0x18000bf82  mov     rcx, [rcx]; StringUuid
0x18000bf85  mov     rsi, [rbp+5Fh]
0x18000bf89  lea     rdx, [rbp+57h+Template.ObjectUuid]; Uuid
0x18000bf8d  call    cs:__imp_UuidFromStringW
0x18000bf93  test    eax, eax
0x18000bf95  jnz     loc_18000C057
0x18000bf9b  or      [rbp+57h+Template.Flags], 1
0x18000bf9f  mov     [rbp+57h+Security.Version], 1
0x18000bfa6  mov     [rbp+57h+Security.ServerPrincName], 0
0x18000bfae  mov     ecx, 5
0x18000bfb3  mov     [rbp+57h+Security.AuthnLevel], ecx
0x18000bfb6  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x18000bfbd  lea     rax, [rbp+57h+var_90]
0x18000bfc1  mov     [rbp+57h+Security.SecurityQos], rax
0x18000bfc5  mov     qword ptr [rbp+57h+var_90], rcx
0x18000bfc9  mov     dword ptr [rbp+57h+var_90+8], 1
0x18000bfd0  mov     qword ptr [rbp+57h+var_90+0Ch], 2
0x18000bfd8  mov     qword ptr [rbp+57h+var_70], 0
0x18000bfe0  mov     dword ptr [rbp+57h+var_70+8], 0
0x18000bfe7  mov     [rbp+57h+var_C0], 1
0x18000bfee  mov     qword ptr [rbx], 0
0x18000bff5  mov     r9, rbx; Binding
0x18000bff8  xor     r8d, r8d; Options
0x18000bffb  lea     rdx, [rbp+57h+Security]; Security
0x18000bfff  lea     rcx, [rbp+57h+Template]; Template
0x18000c003  call    cs:__imp_RpcBindingCreateW
0x18000c009  test    eax, eax
0x18000c00b  jnz     short loc_18000C072
0x18000c00d  mov     r8, [rdi+90h]; IfSpec
0x18000c014  mov     rdx, [rbx]; Binding
0x18000c017  xor     ecx, ecx; pAsync
0x18000c019  call    cs:__imp_RpcBindingBind
0x18000c01f  test    eax, eax
0x18000c021  jnz     short loc_18000C045
0x18000c023  mov     rax, rbx
0x18000c026  mov     rcx, [rbp+57h+var_18]
0x18000c02a  xor     rcx, rsp; StackCookie
0x18000c02d  call    __security_check_cookie
0x18000c032  mov     rbx, [rsp+0E0h+arg_10]
0x18000c03a  add     rsp, 0D0h
0x18000c041  pop     rdi
0x18000c042  pop     rsi
0x18000c043  pop     rbp
0x18000c044  retn
0x18000c045  mov     rcx, [rbp+5Fh]; this
0x18000c049  mov     r9d, eax; char *
0x18000c04c  mov     edx, 6Fh ; 'o'; void *
0x18000c051  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000c057  mov     r9d, 803B0019h; char *
0x18000c05d  lea     r8, aOnecoreVmDvNet_2; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x18000c064  mov     edx, 58h ; 'X'; void *
0x18000c069  mov     rcx, rsi; this
0x18000c06c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c072  mov     rcx, [rbp+5Fh]; this
0x18000c076  mov     r9d, eax; char *
0x18000c079  mov     edx, 6Ch ; 'l'; void *
0x18000c07e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
