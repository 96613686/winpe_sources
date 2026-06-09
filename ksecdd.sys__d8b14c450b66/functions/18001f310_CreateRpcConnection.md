# CreateRpcConnection

- ea: `0x18001f310`
- end: `0x18001f39b`
- name: `CreateRpcConnection`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800011d0`
- `0x18001f870`

## callees

- `0x18000f748`
- `0x18001f310`
- `0x180027d28`

## import_xrefs

- `msrpc!RpcBindingFree` at `0x18001f382`
- `msrpc!RpcBindingFree` at `0x18001f382`
- `msrpc!RpcBindingUnbind` at `0x18001f371`
- `msrpc!RpcBindingUnbind` at `0x18001f371`
- `msrpc!I_RpcExceptionFilter` at `0x180028211`
- `msrpc!I_RpcExceptionFilter` at `0x180028211`

## pseudocode

```c
__int64 __fastcall CreateRpcConnection(__int64 a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 result; // rax
  unsigned int Pointer; // [rsp+30h] [rbp-38h]
  RPC_BINDING_HANDLE Binding[6]; // [rsp+38h] [rbp-30h] BYREF

  Binding[0] = 0;
  result = SecpGetRpcBinding(Binding);
  if ( (int)result >= 0 )
  {
    Pointer = (unsigned int)SspirConnectRpc((__int64)Binding[0], a1, a2, a5, a4, a3).Pointer;
    RpcBindingUnbind(Binding[0]);
    RpcBindingFree(Binding);
    return Pointer;
  }
  return result;
}

```

## disassembly

```asm
0x18001f310  push    rbx
0x18001f312  push    rsi
0x18001f313  push    rdi
0x18001f314  push    r14
0x18001f316  sub     rsp, 48h
0x18001f31a  mov     rbx, r9
0x18001f31d  mov     rdi, r8
0x18001f320  mov     esi, edx
0x18001f322  mov     r14, rcx
0x18001f325  mov     [rsp+68h+Binding], 0
0x18001f32e  lea     rcx, [rsp+68h+Binding]
0x18001f333  call    SecpGetRpcBinding
0x18001f338  test    eax, eax
0x18001f33a  js      short loc_18001F390
0x18001f33c  mov     [rsp+68h+var_40], rdi
0x18001f341  mov     [rsp+68h+var_48], rbx
0x18001f346  mov     r9, [rsp+68h+arg_20]
0x18001f34e  mov     r8d, esi
0x18001f351  mov     rdx, r14
0x18001f354  mov     rcx, [rsp+68h+Binding]
0x18001f359  call    SspirConnectRpc
0x18001f35e  mov     ebx, eax
0x18001f360  mov     [rsp+68h+var_38], eax
0x18001f364  jmp     short loc_18001F36C
0x18001f366  mov     ebx, eax
0x18001f368  mov     [rsp+68h+var_38], eax
0x18001f36c  mov     rcx, [rsp+68h+Binding]; Binding
0x18001f371  call    cs:__imp_RpcBindingUnbind
0x18001f378  nop     dword ptr [rax+rax+00h]
0x18001f37d  lea     rcx, [rsp+68h+Binding]; Binding
0x18001f382  call    cs:__imp_RpcBindingFree
0x18001f389  nop     dword ptr [rax+rax+00h]
0x18001f38e  mov     eax, ebx
0x18001f390  add     rsp, 48h
0x18001f394  pop     r14
0x18001f396  pop     rdi
0x18001f397  pop     rsi
0x18001f398  pop     rbx
0x18001f399  retn
0x180028203  push    rbp
0x180028205  sub     rsp, 30h
0x180028209  mov     rbp, rdx
0x18002820c  mov     rcx, [rcx]
0x18002820f  mov     ecx, [rcx]; ExceptionCode
0x180028211  call    cs:__imp_I_RpcExceptionFilter
0x180028218  nop     dword ptr [rax+rax+00h]
0x18002821d  nop
0x18002821e  add     rsp, 30h
0x180028222  pop     rbp
0x180028223  retn
```
