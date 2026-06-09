# Microsoft::Diagnostics::UtcWrapperBase::Initialize(void)

- ea: `0x180103b10`
- end: `0x180103bbc`
- name: `?Initialize@UtcWrapperBase@Diagnostics@Microsoft@@QEAAJXZ`
- size: `172`
- prototype: `int __fastcall(RPC_BINDING_HANDLE *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800f9ad0`

## callees

- `0x180019000`
- `0x180103b10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180103b39`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180103b39`
- `RPCRT4!RpcStringBindingComposeW` at `0x180103b68`
- `RPCRT4!RpcStringBindingComposeW` at `0x180103b68`
- `RPCRT4!RpcStringFreeW` at `0x180103ba1`
- `RPCRT4!RpcStringFreeW` at `0x180103ba1`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180103b87`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180103b87`

## pseudocode

```c
int __fastcall Microsoft::Diagnostics::UtcWrapperBase::Initialize(RPC_BINDING_HANDLE *this)
{
  int result; // eax
  bool v3; // sf
  RPC_STATUS v4; // eax
  unsigned int v5; // ebx
  RPC_WSTR String; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 ProtSeq[20]; // [rsp+38h] [rbp-40h] BYREF

  _o_wcscpy_s(ProtSeq, 20, L"ncalrpc");
  String = 0;
  result = RpcStringBindingComposeW(0, ProtSeq, 0, 0, 0, &String);
  v3 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v3 = result < 0;
  }
  if ( !v3 )
  {
    v4 = RpcBindingFromStringBindingW(String, this + 1);
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    RpcStringFreeW(&String);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180103b10  push    rbx
0x180103b12  sub     rsp, 70h
0x180103b16  mov     rax, cs:__security_cookie
0x180103b1d  xor     rax, rsp
0x180103b20  mov     [rsp+78h+var_18], rax
0x180103b25  mov     rbx, rcx
0x180103b28  lea     r8, aNcalrpc; "ncalrpc"
0x180103b2f  lea     rcx, [rsp+78h+ProtSeq]
0x180103b34  mov     edx, 14h
0x180103b39  call    cs:__imp__o_wcscpy_s
0x180103b3f  lea     rax, [rsp+78h+String]
0x180103b44  mov     [rsp+78h+String], 0
0x180103b4d  mov     [rsp+78h+StringBinding], rax; StringBinding
0x180103b52  lea     rdx, [rsp+78h+ProtSeq]; ProtSeq
0x180103b57  xor     r9d, r9d; Endpoint
0x180103b5a  mov     [rsp+78h+Options], 0; Options
0x180103b63  xor     r8d, r8d; NetworkAddr
0x180103b66  xor     ecx, ecx; ObjUuid
0x180103b68  call    cs:__imp_RpcStringBindingComposeW
0x180103b6e  test    eax, eax
0x180103b70  jle     short loc_180103B7C
0x180103b72  movzx   eax, ax
0x180103b75  or      eax, 80070000h
0x180103b7a  test    eax, eax
0x180103b7c  js      short loc_180103BA9
0x180103b7e  mov     rcx, [rsp+78h+String]; StringBinding
0x180103b83  lea     rdx, [rbx+8]; Binding
0x180103b87  call    cs:__imp_RpcBindingFromStringBindingW
0x180103b8d  mov     ebx, eax
0x180103b8f  test    eax, eax
0x180103b91  jle     short loc_180103B9C
0x180103b93  movzx   ebx, ax
0x180103b96  or      ebx, 80070000h
0x180103b9c  lea     rcx, [rsp+78h+String]; String
0x180103ba1  call    cs:__imp_RpcStringFreeW
0x180103ba7  mov     eax, ebx
0x180103ba9  mov     rcx, [rsp+78h+var_18]
0x180103bae  xor     rcx, rsp; StackCookie
0x180103bb1  call    __security_check_cookie
0x180103bb6  add     rsp, 70h
0x180103bba  pop     rbx
0x180103bbb  retn
```
