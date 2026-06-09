# STRING_HANDLE_bind_helper

- ea: `0x180002b00`
- end: `0x180002bef`
- name: `STRING_HANDLE_bind_helper`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002af0`

## callees

- `0x180002b00`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180002bb7`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180002bb7`
- `RPCRT4!RpcBindingSetOption` at `0x180002b91`
- `RPCRT4!RpcBindingSetOption` at `0x180002b91`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180002b65`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180002b65`
- `RPCRT4!RpcStringBindingComposeW` at `0x180002b48`
- `RPCRT4!RpcStringBindingComposeW` at `0x180002b48`
- `RPCRT4!RpcBindingFree` at `0x180002bd0`
- `RPCRT4!RpcBindingFree` at `0x180002bd0`
- `RPCRT4!RpcStringFreeW` at `0x180002b72`
- `RPCRT4!RpcStringFreeW` at `0x180002b72`

## string_xrefs

- `0x180002b33`: `Security=Impersonation Dynamic False`

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
          (RPC_WSTR)L"dhcpcsvc",
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
0x180002b00  mov     [rsp+Binding], rdx
0x180002b05  push    rdi
0x180002b06  sub     rsp, 30h
0x180002b0a  xor     edi, edi
0x180002b0c  mov     [rsp+38h+String], rdi
0x180002b11  mov     [rsp+38h+Binding], rdi
0x180002b16  test    rcx, rcx
0x180002b19  jnz     loc_180002BDE
0x180002b1f  lea     rax, [rsp+38h+String]
0x180002b24  xor     r8d, r8d; NetworkAddr
0x180002b27  mov     [rsp+38h+StringBinding], rax; StringBinding
0x180002b2c  lea     r9, Endpoint; "dhcpcsvc"
0x180002b33  lea     rax, Options; "Security=Impersonation Dynamic False"
0x180002b3a  xor     ecx, ecx; ObjUuid
0x180002b3c  lea     rdx, ProtSeq; "ncalrpc"
0x180002b43  mov     [rsp+38h+Options], rax; Options
0x180002b48  call    cs:__imp_RpcStringBindingComposeW
0x180002b4e  test    eax, eax
0x180002b50  jnz     loc_180002BD6
0x180002b56  mov     rcx, [rsp+38h+String]; StringBinding
0x180002b5b  lea     rdx, [rsp+38h+Binding]; Binding
0x180002b60  mov     [rsp+38h+arg_18], rbx
0x180002b65  call    cs:__imp_RpcBindingFromStringBindingW
0x180002b6b  lea     rcx, [rsp+38h+String]; String
0x180002b70  mov     ebx, eax
0x180002b72  call    cs:__imp_RpcStringFreeW
0x180002b78  test    ebx, ebx
0x180002b7a  mov     rbx, [rsp+38h+arg_18]
0x180002b7f  jnz     short loc_180002BD6
0x180002b81  mov     rcx, [rsp+38h+Binding]; hBinding
0x180002b86  mov     edx, 0Bh; option
0x180002b8b  mov     r8d, 1; optionValue
0x180002b91  call    cs:__imp_RpcBindingSetOption
0x180002b97  test    eax, eax
0x180002b99  jnz     short loc_180002BE8
0x180002b9b  mov     rcx, [rsp+38h+Binding]; Binding
0x180002ba0  xor     edx, edx; ServerPrincName
0x180002ba2  mov     dword ptr [rsp+38h+StringBinding], edi; AuthzSvc
0x180002ba6  mov     r9d, 0Ah; AuthnSvc
0x180002bac  mov     r8d, 6; AuthnLevel
0x180002bb2  mov     [rsp+38h+Options], rdi; AuthIdentity
0x180002bb7  call    cs:__imp_RpcBindingSetAuthInfoW
0x180002bbd  test    eax, eax
0x180002bbf  mov     rax, [rsp+38h+Binding]
0x180002bc4  jz      short loc_180002BD8
0x180002bc6  lea     rcx, [rsp+38h+arg_10]; Binding
0x180002bcb  mov     [rsp+38h+arg_10], rax
0x180002bd0  call    cs:__imp_RpcBindingFree
0x180002bd6  xor     eax, eax
0x180002bd8  add     rsp, 30h
0x180002bdc  pop     rdi
0x180002bdd  retn
0x180002bde  cmp     [rcx], di
0x180002be1  jnz     short loc_180002BD6
0x180002be3  jmp     loc_180002B1F
0x180002be8  mov     rax, [rsp+38h+Binding]
0x180002bed  jmp     short loc_180002BC6
```
