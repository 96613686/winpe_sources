# LsapCreateBindingHandleForLocal

- ea: `0x18004f584`
- end: `0x18004f64c`
- name: `LsapCreateBindingHandleForLocal`
- size: `200`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004f660`
- `0x18004f6c0`
- `0x18004f700`

## callees

- `0x18003a730`
- `0x18004f584`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x18004f5e8`
- `RPCRT4!RpcBindingCreateW` at `0x18004f5e8`
- `RPCRT4!RpcBindingBind` at `0x18004f601`
- `RPCRT4!RpcBindingBind` at `0x18004f601`
- `RPCRT4!I_RpcMapWin32Status` at `0x18004f628`
- `RPCRT4!I_RpcMapWin32Status` at `0x18004f628`
- `RPCRT4!RpcBindingFree` at `0x18004f617`
- `RPCRT4!RpcBindingFree` at `0x18004f617`

## pseudocode

```c
int __fastcall LsapCreateBindingHandleForLocal(unsigned __int16 *a1, __int64 a2, _QWORD *a3)
{
  RPC_STATUS v4; // ebx
  RPC_BINDING_HANDLE v5; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-50h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+28h] [rbp-48h] BYREF

  Binding = 0;
  memset(&Template, 0, 24);
  Template.StringEndpoint = a1;
  Template.Version = 1;
  Template.ProtocolSequence = 3;
  memset(&Template.u1, 0, 24);
  v4 = RpcBindingCreateW(&Template, (RPC_BINDING_HANDLE_SECURITY_V1_W *)&g_LsapBindingHandleSecurity, 0, &Binding);
  if ( v4 || (v4 = RpcBindingBind(0, Binding, qword_1800589E0)) != 0 )
  {
    RpcBindingFree(&Binding);
    v5 = 0;
    Binding = 0;
  }
  else
  {
    v5 = Binding;
  }
  *a3 = v5;
  return I_RpcMapWin32Status(v4);
}

```

## disassembly

```asm
0x18004f584  mov     [rsp-8+arg_8], rbx
0x18004f589  mov     [rsp-8+arg_18], rdi
0x18004f58e  push    rbp
0x18004f58f  mov     rbp, rsp
0x18004f592  sub     rsp, 70h
0x18004f596  mov     rax, cs:__security_cookie
0x18004f59d  xor     rax, rsp
0x18004f5a0  mov     [rbp+var_10], rax
0x18004f5a4  xorps   xmm0, xmm0
0x18004f5a7  mov     [rbp+Binding], 0
0x18004f5af  movups  xmmword ptr [rbp+Template.Version], xmm0
0x18004f5b3  mov     rdi, r8
0x18004f5b6  xor     eax, eax
0x18004f5b8  movups  xmmword ptr [rbp+Template.NetworkAddress], xmm0
0x18004f5bc  mov     [rbp+Template.StringEndpoint], rcx
0x18004f5c0  lea     r9, [rbp+Binding]; Binding
0x18004f5c4  lea     rcx, [rbp+Template]; Template
0x18004f5c8  mov     qword ptr [rbp+Template.ObjectUuid.Data4], rax
0x18004f5cc  xor     r8d, r8d; Options
0x18004f5cf  mov     [rbp+Template.Version], 1
0x18004f5d6  lea     rdx, g_LsapBindingHandleSecurity; Security
0x18004f5dd  mov     [rbp+Template.ProtocolSequence], 3
0x18004f5e4  movups  xmmword ptr [rbp+Template.u1], xmm0
0x18004f5e8  call    cs:__imp_RpcBindingCreateW
0x18004f5ee  mov     ebx, eax
0x18004f5f0  test    eax, eax
0x18004f5f2  jnz     short loc_18004F613
0x18004f5f4  mov     rdx, [rbp+Binding]; Binding
0x18004f5f8  lea     r8, qword_1800589E0; IfSpec
0x18004f5ff  xor     ecx, ecx; pAsync
0x18004f601  call    cs:__imp_RpcBindingBind
0x18004f607  mov     ebx, eax
0x18004f609  test    eax, eax
0x18004f60b  jnz     short loc_18004F613
0x18004f60d  mov     rax, [rbp+Binding]
0x18004f611  jmp     short loc_18004F623
0x18004f613  lea     rcx, [rbp+Binding]; Binding
0x18004f617  call    cs:__imp_RpcBindingFree
0x18004f61d  xor     eax, eax
0x18004f61f  mov     [rbp+Binding], rax
0x18004f623  mov     ecx, ebx; Status
0x18004f625  mov     [rdi], rax
0x18004f628  call    cs:__imp_I_RpcMapWin32Status
0x18004f62e  mov     rcx, [rbp+var_10]
0x18004f632  xor     rcx, rsp; StackCookie
0x18004f635  call    __security_check_cookie
0x18004f63a  lea     r11, [rsp+70h+var_s0]
0x18004f63f  mov     rbx, [r11+18h]
0x18004f643  mov     rdi, [r11+28h]
0x18004f647  mov     rsp, r11
0x18004f64a  pop     rbp
0x18004f64b  retn
```
