# STRING_HANDLE_bind_helper

- ea: `0x180002260`
- end: `0x18000234f`
- name: `STRING_HANDLE_bind_helper`
- size: `239`
- prototype: `RPC_BINDING_HANDLE __fastcall(_WORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002250`

## callees

- `0x180002260`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180002317`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180002317`
- `RPCRT4!RpcBindingSetOption` at `0x1800022f1`
- `RPCRT4!RpcBindingSetOption` at `0x1800022f1`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800022c5`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800022c5`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800022a8`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800022a8`
- `RPCRT4!RpcBindingFree` at `0x180002330`
- `RPCRT4!RpcBindingFree` at `0x180002330`
- `RPCRT4!RpcStringFreeW` at `0x1800022d2`
- `RPCRT4!RpcStringFreeW` at `0x1800022d2`

## string_xrefs

- `0x180002293`: `Security=Impersonation Dynamic False`

## pseudocode

```c
RPC_BINDING_HANDLE __fastcall STRING_HANDLE_bind_helper(_WORD *a1)
{
  RPC_STATUS v1; // ebx
  bool v2; // zf
  RPC_BINDING_HANDLE result; // rax
  RPC_WSTR String; // [rsp+40h] [rbp+8h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+48h] [rbp+10h] BYREF
  RPC_BINDING_HANDLE v6; // [rsp+50h] [rbp+18h] BYREF

  String = 0;
  Binding = 0;
  if ( (!a1 || !*a1)
    && !RpcStringBindingComposeW(
          0,
          (RPC_WSTR)L"ncalrpc",
          0,
          (RPC_WSTR)L"dhcpcsvc6",
          (RPC_WSTR)L"Security=Impersonation Dynamic False",
          &String) )
  {
    v1 = RpcBindingFromStringBindingW(String, &Binding);
    RpcStringFreeW(&String);
    if ( !v1 )
    {
      if ( RpcBindingSetOption(Binding, 0xBu, 1u) )
      {
        result = Binding;
      }
      else
      {
        v2 = RpcBindingSetAuthInfoW(Binding, 0, 6u, 0xAu, 0, 0) == 0;
        result = Binding;
        if ( v2 )
          return result;
      }
      v6 = result;
      RpcBindingFree(&v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180002260  mov     [rsp+Binding], rdx
0x180002265  push    rdi
0x180002266  sub     rsp, 30h
0x18000226a  xor     edi, edi
0x18000226c  mov     [rsp+38h+String], rdi
0x180002271  mov     [rsp+38h+Binding], rdi
0x180002276  test    rcx, rcx
0x180002279  jnz     loc_18000233E
0x18000227f  lea     rax, [rsp+38h+String]
0x180002284  xor     r8d, r8d; NetworkAddr
0x180002287  mov     [rsp+38h+StringBinding], rax; StringBinding
0x18000228c  lea     r9, Endpoint; "dhcpcsvc6"
0x180002293  lea     rax, Options; "Security=Impersonation Dynamic False"
0x18000229a  xor     ecx, ecx; ObjUuid
0x18000229c  lea     rdx, ProtSeq; "ncalrpc"
0x1800022a3  mov     [rsp+38h+Options], rax; Options
0x1800022a8  call    cs:__imp_RpcStringBindingComposeW
0x1800022ae  test    eax, eax
0x1800022b0  jnz     loc_180002336
0x1800022b6  mov     rcx, [rsp+38h+String]; StringBinding
0x1800022bb  lea     rdx, [rsp+38h+Binding]; Binding
0x1800022c0  mov     [rsp+38h+arg_18], rbx
0x1800022c5  call    cs:__imp_RpcBindingFromStringBindingW
0x1800022cb  lea     rcx, [rsp+38h+String]; String
0x1800022d0  mov     ebx, eax
0x1800022d2  call    cs:__imp_RpcStringFreeW
0x1800022d8  test    ebx, ebx
0x1800022da  mov     rbx, [rsp+38h+arg_18]
0x1800022df  jnz     short loc_180002336
0x1800022e1  mov     rcx, [rsp+38h+Binding]; hBinding
0x1800022e6  mov     edx, 0Bh; option
0x1800022eb  mov     r8d, 1; optionValue
0x1800022f1  call    cs:__imp_RpcBindingSetOption
0x1800022f7  test    eax, eax
0x1800022f9  jnz     short loc_180002348
0x1800022fb  mov     rcx, [rsp+38h+Binding]; Binding
0x180002300  xor     edx, edx; ServerPrincName
0x180002302  mov     dword ptr [rsp+38h+StringBinding], edi; AuthzSvc
0x180002306  mov     r9d, 0Ah; AuthnSvc
0x18000230c  mov     r8d, 6; AuthnLevel
0x180002312  mov     [rsp+38h+Options], rdi; AuthIdentity
0x180002317  call    cs:__imp_RpcBindingSetAuthInfoW
0x18000231d  test    eax, eax
0x18000231f  mov     rax, [rsp+38h+Binding]
0x180002324  jz      short loc_180002338
0x180002326  lea     rcx, [rsp+38h+arg_10]; Binding
0x18000232b  mov     [rsp+38h+arg_10], rax
0x180002330  call    cs:__imp_RpcBindingFree
0x180002336  xor     eax, eax
0x180002338  add     rsp, 30h
0x18000233c  pop     rdi
0x18000233d  retn
0x18000233e  cmp     [rcx], di
0x180002341  jnz     short loc_180002336
0x180002343  jmp     loc_18000227F
0x180002348  mov     rax, [rsp+38h+Binding]
0x18000234d  jmp     short loc_180002326
```
