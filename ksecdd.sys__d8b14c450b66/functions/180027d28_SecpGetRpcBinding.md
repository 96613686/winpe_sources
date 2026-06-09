# SecpGetRpcBinding

- ea: `0x180027d28`
- end: `0x180027e50`
- name: `SecpGetRpcBinding`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001f310`

## callees

- `0x180010840`
- `0x180027d28`

## import_xrefs

- `msrpc!RpcBindingBind` at `0x180027e04`
- `msrpc!RpcBindingBind` at `0x180027e04`
- `msrpc!RpcBindingCreateW` at `0x180027de5`
- `msrpc!RpcBindingCreateW` at `0x180027de5`
- `msrpc!RpcBindingFree` at `0x180027e20`
- `msrpc!RpcBindingFree` at `0x180027e20`

## pseudocode

```c
__int64 __fastcall SecpGetRpcBinding(RPC_BINDING_HANDLE *a1)
{
  RPC_STATUS v2; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-79h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+28h] [rbp-71h] BYREF
  _DWORD v6[4]; // [rsp+50h] [rbp-49h] BYREF
  __int128 v7; // [rsp+60h] [rbp-39h]
  _DWORD *v8; // [rsp+70h] [rbp-29h]
  __int64 v9; // [rsp+78h] [rbp-21h]
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+80h] [rbp-19h] BYREF
  _DWORD v11[4]; // [rsp+B8h] [rbp+1Fh] BYREF

  v11[0] = 257;
  Binding = 0;
  v11[1] = 83886080;
  v11[2] = 18;
  v6[1] = 1;
  memset(&Template, 0, 24);
  Template.Version = 1;
  Template.StringEndpoint = L"lsasspirpc";
  Template.ProtocolSequence = 3;
  v8 = v11;
  v6[2] = 1;
  v6[3] = 3;
  Security.Version = 1;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v6;
  memset(&Template.u1, 0, 24);
  v9 = 0;
  v7 = 0;
  v6[0] = 4;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  v2 = RpcBindingCreateW(&Template, &Security, 0, &Binding);
  if ( !v2 )
    v2 = RpcBindingBind(0, Binding, qword_180014FB0);
  if ( v2 >= 0 )
  {
    *a1 = Binding;
  }
  else if ( Binding )
  {
    RpcBindingFree(&Binding);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180027d28  push    rbp
0x180027d2a  push    rbx
0x180027d2b  push    rsi
0x180027d2c  push    rdi
0x180027d2d  lea     rbp, [rsp-3Fh]
0x180027d32  sub     rsp, 0D8h
0x180027d39  mov     rax, cs:__security_cookie
0x180027d40  xor     rax, rsp
0x180027d43  mov     [rbp+57h+var_28], rax
0x180027d47  xor     esi, esi
0x180027d49  mov     [rbp+57h+var_38], 101h
0x180027d50  xor     eax, eax
0x180027d52  mov     [rbp+57h+Binding], rsi
0x180027d56  xorps   xmm0, xmm0
0x180027d59  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data4], rax
0x180027d5d  mov     rdi, rcx
0x180027d60  mov     [rbp+57h+var_34], 5000000h
0x180027d67  lea     edx, [rsi+1]
0x180027d6a  mov     [rbp+57h+var_30], 12h
0x180027d71  lea     ecx, [rsi+3]
0x180027d74  mov     [rbp+57h+var_9C], edx
0x180027d77  movups  xmmword ptr [rbp+57h+Template.Version], xmm0
0x180027d7b  lea     rax, aLsasspirpc; "lsasspirpc"
0x180027d82  mov     [rbp+57h+Template.Version], edx
0x180027d85  movups  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x180027d89  mov     [rbp+57h+Template.StringEndpoint], rax
0x180027d8d  lea     r9, [rbp+57h+Binding]; Binding
0x180027d91  lea     rax, [rbp+57h+var_38]
0x180027d95  mov     [rbp+57h+Template.ProtocolSequence], ecx
0x180027d98  mov     [rbp+57h+var_80], rax
0x180027d9c  xor     r8d, r8d; Options
0x180027d9f  lea     rax, [rbp+57h+var_A0]
0x180027da3  mov     [rbp+57h+var_98], edx
0x180027da6  mov     [rbp+57h+var_94], ecx
0x180027da9  lea     rcx, [rbp+57h+Template]; Template
0x180027dad  mov     [rbp+57h+Security.Version], edx
0x180027db0  lea     rdx, [rbp+57h+Security]; Security
0x180027db4  mov     [rbp+57h+Security.SecurityQos], rax
0x180027db8  movups  xmmword ptr [rbp+57h+Template.u1], xmm0
0x180027dbc  mov     [rbp+57h+var_78], rsi
0x180027dc0  movdqu  [rbp+57h+var_90], xmm0
0x180027dc5  mov     [rbp+57h+var_A0], 4
0x180027dcc  mov     qword ptr [rbp+57h+Security+4], rsi
0x180027dd0  mov     dword ptr [rbp+57h+Security.ServerPrincName+4], esi
0x180027dd3  mov     [rbp+57h+Security.AuthIdentity], rsi
0x180027dd7  mov     [rbp+57h+Security.AuthnLevel], 6
0x180027dde  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x180027de5  call    cs:__imp_RpcBindingCreateW
0x180027dec  nop     dword ptr [rax+rax+00h]
0x180027df1  mov     ebx, eax
0x180027df3  test    eax, eax
0x180027df5  jnz     short loc_180027E12
0x180027df7  mov     rdx, [rbp+57h+Binding]; Binding
0x180027dfb  lea     r8, qword_180014FB0; IfSpec
0x180027e02  xor     ecx, ecx; pAsync
0x180027e04  call    cs:__imp_RpcBindingBind
0x180027e0b  nop     dword ptr [rax+rax+00h]
0x180027e10  mov     ebx, eax
0x180027e12  test    ebx, ebx
0x180027e14  jns     short loc_180027E2E
0x180027e16  cmp     [rbp+57h+Binding], rsi
0x180027e1a  jz      short loc_180027E35
0x180027e1c  lea     rcx, [rbp+57h+Binding]; Binding
0x180027e20  call    cs:__imp_RpcBindingFree
0x180027e27  nop     dword ptr [rax+rax+00h]
0x180027e2c  jmp     short loc_180027E35
0x180027e2e  mov     rax, [rbp+57h+Binding]
0x180027e32  mov     [rdi], rax
0x180027e35  mov     eax, ebx
0x180027e37  mov     rcx, [rbp+57h+var_28]
0x180027e3b  xor     rcx, rsp; StackCookie
0x180027e3e  call    __security_check_cookie
0x180027e43  add     rsp, 0D8h
0x180027e4a  pop     rdi
0x180027e4b  pop     rsi
0x180027e4c  pop     rbx
0x180027e4d  pop     rbp
0x180027e4e  retn
```
