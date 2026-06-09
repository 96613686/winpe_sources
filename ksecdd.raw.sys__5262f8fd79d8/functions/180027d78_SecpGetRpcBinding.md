# SecpGetRpcBinding

- ea: `0x180027d78`
- end: `0x180027ea0`
- name: `SecpGetRpcBinding`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001f310`

## callees

- `0x1800108a0`
- `0x180027d78`

## import_xrefs

- `msrpc!RpcBindingBind` at `0x180027e54`
- `msrpc!RpcBindingBind` at `0x180027e54`
- `msrpc!RpcBindingCreateW` at `0x180027e35`
- `msrpc!RpcBindingCreateW` at `0x180027e35`
- `msrpc!RpcBindingFree` at `0x180027e70`
- `msrpc!RpcBindingFree` at `0x180027e70`

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
    v2 = RpcBindingBind(0, Binding, &unk_180014FB0);
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
0x180027d78  push    rbp
0x180027d7a  push    rbx
0x180027d7b  push    rsi
0x180027d7c  push    rdi
0x180027d7d  lea     rbp, [rsp-3Fh]
0x180027d82  sub     rsp, 0D8h
0x180027d89  mov     rax, cs:__security_cookie
0x180027d90  xor     rax, rsp
0x180027d93  mov     [rbp+57h+var_28], rax
0x180027d97  xor     esi, esi
0x180027d99  mov     [rbp+57h+var_38], 101h
0x180027da0  xor     eax, eax
0x180027da2  mov     [rbp+57h+Binding], rsi
0x180027da6  xorps   xmm0, xmm0
0x180027da9  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data4], rax
0x180027dad  mov     rdi, rcx
0x180027db0  mov     [rbp+57h+var_34], 5000000h
0x180027db7  lea     edx, [rsi+1]
0x180027dba  mov     [rbp+57h+var_30], 12h
0x180027dc1  lea     ecx, [rsi+3]
0x180027dc4  mov     [rbp+57h+var_9C], edx
0x180027dc7  movups  xmmword ptr [rbp+57h+Template.Version], xmm0
0x180027dcb  lea     rax, aLsasspirpc; "lsasspirpc"
0x180027dd2  mov     [rbp+57h+Template.Version], edx
0x180027dd5  movups  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x180027dd9  mov     [rbp+57h+Template.StringEndpoint], rax
0x180027ddd  lea     r9, [rbp+57h+Binding]; Binding
0x180027de1  lea     rax, [rbp+57h+var_38]
0x180027de5  mov     [rbp+57h+Template.ProtocolSequence], ecx
0x180027de8  mov     [rbp+57h+var_80], rax
0x180027dec  xor     r8d, r8d; Options
0x180027def  lea     rax, [rbp+57h+var_A0]
0x180027df3  mov     [rbp+57h+var_98], edx
0x180027df6  mov     [rbp+57h+var_94], ecx
0x180027df9  lea     rcx, [rbp+57h+Template]; Template
0x180027dfd  mov     [rbp+57h+Security.Version], edx
0x180027e00  lea     rdx, [rbp+57h+Security]; Security
0x180027e04  mov     [rbp+57h+Security.SecurityQos], rax
0x180027e08  movups  xmmword ptr [rbp+57h+Template.u1], xmm0
0x180027e0c  mov     [rbp+57h+var_78], rsi
0x180027e10  movdqu  [rbp+57h+var_90], xmm0
0x180027e15  mov     [rbp+57h+var_A0], 4
0x180027e1c  mov     qword ptr [rbp+57h+Security+4], rsi
0x180027e20  mov     dword ptr [rbp+57h+Security.ServerPrincName+4], esi
0x180027e23  mov     [rbp+57h+Security.AuthIdentity], rsi
0x180027e27  mov     [rbp+57h+Security.AuthnLevel], 6
0x180027e2e  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x180027e35  call    cs:__imp_RpcBindingCreateW
0x180027e3c  nop     dword ptr [rax+rax+00h]
0x180027e41  mov     ebx, eax
0x180027e43  test    eax, eax
0x180027e45  jnz     short loc_180027E62
0x180027e47  mov     rdx, [rbp+57h+Binding]; Binding
0x180027e4b  lea     r8, unk_180014FB0; IfSpec
0x180027e52  xor     ecx, ecx; pAsync
0x180027e54  call    cs:__imp_RpcBindingBind
0x180027e5b  nop     dword ptr [rax+rax+00h]
0x180027e60  mov     ebx, eax
0x180027e62  test    ebx, ebx
0x180027e64  jns     short loc_180027E7E
0x180027e66  cmp     [rbp+57h+Binding], rsi
0x180027e6a  jz      short loc_180027E85
0x180027e6c  lea     rcx, [rbp+57h+Binding]; Binding
0x180027e70  call    cs:__imp_RpcBindingFree
0x180027e77  nop     dword ptr [rax+rax+00h]
0x180027e7c  jmp     short loc_180027E85
0x180027e7e  mov     rax, [rbp+57h+Binding]
0x180027e82  mov     [rdi], rax
0x180027e85  mov     eax, ebx
0x180027e87  mov     rcx, [rbp+57h+var_28]
0x180027e8b  xor     rcx, rsp; StackCookie
0x180027e8e  call    __security_check_cookie
0x180027e93  add     rsp, 0D8h
0x180027e9a  pop     rdi
0x180027e9b  pop     rsi
0x180027e9c  pop     rbx
0x180027e9d  pop     rbp
0x180027e9e  retn
```
