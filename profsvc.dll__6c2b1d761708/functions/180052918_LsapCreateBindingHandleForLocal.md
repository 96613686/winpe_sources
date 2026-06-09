# LsapCreateBindingHandleForLocal

- ea: `0x180052918`
- end: `0x1800529f9`
- name: `LsapCreateBindingHandleForLocal`
- size: `225`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180052a00`
- `0x180052a60`
- `0x180052aa0`

## callees

- `0x18003bc70`
- `0x180052918`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x18005297c`
- `RPCRT4!RpcBindingCreateW` at `0x18005297c`
- `RPCRT4!RpcBindingBind` at `0x18005299b`
- `RPCRT4!RpcBindingBind` at `0x18005299b`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800529ce`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800529ce`
- `RPCRT4!RpcBindingFree` at `0x1800529b7`
- `RPCRT4!RpcBindingFree` at `0x1800529b7`

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
  if ( v4 || (v4 = RpcBindingBind(0, Binding, qword_18005B9D0)) != 0 )
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
0x180052918  mov     [rsp-8+arg_8], rbx
0x18005291d  mov     [rsp-8+arg_18], rdi
0x180052922  push    rbp
0x180052923  mov     rbp, rsp
0x180052926  sub     rsp, 70h
0x18005292a  mov     rax, cs:__security_cookie
0x180052931  xor     rax, rsp
0x180052934  mov     [rbp+var_10], rax
0x180052938  xorps   xmm0, xmm0
0x18005293b  mov     [rbp+Binding], 0
0x180052943  movups  xmmword ptr [rbp+Template.Version], xmm0
0x180052947  mov     rdi, r8
0x18005294a  xor     eax, eax
0x18005294c  movups  xmmword ptr [rbp+Template.NetworkAddress], xmm0
0x180052950  mov     [rbp+Template.StringEndpoint], rcx
0x180052954  lea     r9, [rbp+Binding]; Binding
0x180052958  lea     rcx, [rbp+Template]; Template
0x18005295c  mov     qword ptr [rbp+Template.ObjectUuid.Data4], rax
0x180052960  xor     r8d, r8d; Options
0x180052963  mov     [rbp+Template.Version], 1
0x18005296a  lea     rdx, g_LsapBindingHandleSecurity; Security
0x180052971  mov     [rbp+Template.ProtocolSequence], 3
0x180052978  movups  xmmword ptr [rbp+Template.u1], xmm0
0x18005297c  call    cs:__imp_RpcBindingCreateW
0x180052983  nop     dword ptr [rax+rax+00h]
0x180052988  mov     ebx, eax
0x18005298a  test    eax, eax
0x18005298c  jnz     short loc_1800529B3
0x18005298e  mov     rdx, [rbp+Binding]; Binding
0x180052992  lea     r8, qword_18005B9D0; IfSpec
0x180052999  xor     ecx, ecx; pAsync
0x18005299b  call    cs:__imp_RpcBindingBind
0x1800529a2  nop     dword ptr [rax+rax+00h]
0x1800529a7  mov     ebx, eax
0x1800529a9  test    eax, eax
0x1800529ab  jnz     short loc_1800529B3
0x1800529ad  mov     rax, [rbp+Binding]
0x1800529b1  jmp     short loc_1800529C9
0x1800529b3  lea     rcx, [rbp+Binding]; Binding
0x1800529b7  call    cs:__imp_RpcBindingFree
0x1800529be  nop     dword ptr [rax+rax+00h]
0x1800529c3  xor     eax, eax
0x1800529c5  mov     [rbp+Binding], rax
0x1800529c9  mov     ecx, ebx; Status
0x1800529cb  mov     [rdi], rax
0x1800529ce  call    cs:__imp_I_RpcMapWin32Status
0x1800529d5  nop     dword ptr [rax+rax+00h]
0x1800529da  mov     rcx, [rbp+var_10]
0x1800529de  xor     rcx, rsp; StackCookie
0x1800529e1  call    __security_check_cookie
0x1800529e6  lea     r11, [rsp+70h+var_s0]
0x1800529eb  mov     rbx, [r11+18h]
0x1800529ef  mov     rdi, [r11+28h]
0x1800529f3  mov     rsp, r11
0x1800529f6  pop     rbp
0x1800529f7  retn
```
