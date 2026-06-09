# LsapCreateBindingHandleForLocal

- ea: `0x1801830c0`
- end: `0x180183188`
- name: `LsapCreateBindingHandleForLocal`
- size: `200`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180183190`
- `0x1801831f0`
- `0x180183230`

## callees

- `0x180008dc0`
- `0x1801830c0`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x180183124`
- `RPCRT4!RpcBindingCreateW` at `0x180183124`
- `RPCRT4!I_RpcMapWin32Status` at `0x180183164`
- `RPCRT4!I_RpcMapWin32Status` at `0x180183164`
- `RPCRT4!RpcBindingBind` at `0x18018313d`
- `RPCRT4!RpcBindingBind` at `0x18018313d`
- `RPCRT4!RpcBindingFree` at `0x180183153`
- `RPCRT4!RpcBindingFree` at `0x180183153`

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
  if ( v4 || (v4 = RpcBindingBind(0, Binding, qword_1801A9E50)) != 0 )
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
0x1801830c0  mov     [rsp-8+arg_8], rbx
0x1801830c5  mov     [rsp-8+arg_18], rdi
0x1801830ca  push    rbp
0x1801830cb  mov     rbp, rsp
0x1801830ce  sub     rsp, 70h
0x1801830d2  mov     rax, cs:__security_cookie
0x1801830d9  xor     rax, rsp
0x1801830dc  mov     [rbp+var_10], rax
0x1801830e0  xorps   xmm0, xmm0
0x1801830e3  mov     [rbp+Binding], 0
0x1801830eb  movups  xmmword ptr [rbp+Template.Version], xmm0
0x1801830ef  mov     rdi, r8
0x1801830f2  xor     eax, eax
0x1801830f4  movups  xmmword ptr [rbp+Template.NetworkAddress], xmm0
0x1801830f8  mov     [rbp+Template.StringEndpoint], rcx
0x1801830fc  lea     r9, [rbp+Binding]; Binding
0x180183100  lea     rcx, [rbp+Template]; Template
0x180183104  mov     qword ptr [rbp+Template.ObjectUuid.Data4], rax
0x180183108  xor     r8d, r8d; Options
0x18018310b  mov     [rbp+Template.Version], 1
0x180183112  lea     rdx, g_LsapBindingHandleSecurity; Security
0x180183119  mov     [rbp+Template.ProtocolSequence], 3
0x180183120  movups  xmmword ptr [rbp+Template.u1], xmm0
0x180183124  call    cs:__imp_RpcBindingCreateW
0x18018312a  mov     ebx, eax
0x18018312c  test    eax, eax
0x18018312e  jnz     short loc_18018314F
0x180183130  mov     rdx, [rbp+Binding]; Binding
0x180183134  lea     r8, qword_1801A9E50; IfSpec
0x18018313b  xor     ecx, ecx; pAsync
0x18018313d  call    cs:__imp_RpcBindingBind
0x180183143  mov     ebx, eax
0x180183145  test    eax, eax
0x180183147  jnz     short loc_18018314F
0x180183149  mov     rax, [rbp+Binding]
0x18018314d  jmp     short loc_18018315F
0x18018314f  lea     rcx, [rbp+Binding]; Binding
0x180183153  call    cs:__imp_RpcBindingFree
0x180183159  xor     eax, eax
0x18018315b  mov     [rbp+Binding], rax
0x18018315f  mov     ecx, ebx; Status
0x180183161  mov     [rdi], rax
0x180183164  call    cs:__imp_I_RpcMapWin32Status
0x18018316a  mov     rcx, [rbp+var_10]
0x18018316e  xor     rcx, rsp; StackCookie
0x180183171  call    __security_check_cookie
0x180183176  lea     r11, [rsp+70h+var_s0]
0x18018317b  mov     rbx, [r11+18h]
0x18018317f  mov     rdi, [r11+28h]
0x180183183  mov     rsp, r11
0x180183186  pop     rbp
0x180183187  retn
```
