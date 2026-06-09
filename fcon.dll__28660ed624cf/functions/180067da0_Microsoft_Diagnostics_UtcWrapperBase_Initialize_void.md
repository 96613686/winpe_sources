# Microsoft::Diagnostics::UtcWrapperBase::Initialize(void)

- ea: `0x180067da0`
- end: `0x180067e4c`
- name: `?Initialize@UtcWrapperBase@Diagnostics@Microsoft@@QEAAJXZ`
- size: `172`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UtcWrapperBase *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180067694`

## callees

- `0x180003220`
- `0x180067da0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180067dc9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180067dc9`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180067e17`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180067e17`
- `RPCRT4!RpcStringBindingComposeW` at `0x180067df8`
- `RPCRT4!RpcStringBindingComposeW` at `0x180067df8`
- `RPCRT4!RpcStringFreeW` at `0x180067e31`
- `RPCRT4!RpcStringFreeW` at `0x180067e31`

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
0x180067da0  push    rbx
0x180067da2  sub     rsp, 70h
0x180067da6  mov     rax, cs:__security_cookie
0x180067dad  xor     rax, rsp
0x180067db0  mov     [rsp+78h+var_18], rax
0x180067db5  mov     rbx, rcx
0x180067db8  lea     r8, aNcalrpc; "ncalrpc"
0x180067dbf  lea     rcx, [rsp+78h+ProtSeq]
0x180067dc4  mov     edx, 14h
0x180067dc9  call    cs:__imp__o_wcscpy_s
0x180067dcf  lea     rax, [rsp+78h+String]
0x180067dd4  mov     [rsp+78h+String], 0
0x180067ddd  mov     [rsp+78h+StringBinding], rax; StringBinding
0x180067de2  lea     rdx, [rsp+78h+ProtSeq]; ProtSeq
0x180067de7  xor     r9d, r9d; Endpoint
0x180067dea  mov     [rsp+78h+Options], 0; Options
0x180067df3  xor     r8d, r8d; NetworkAddr
0x180067df6  xor     ecx, ecx; ObjUuid
0x180067df8  call    cs:__imp_RpcStringBindingComposeW
0x180067dfe  test    eax, eax
0x180067e00  jle     short loc_180067E0C
0x180067e02  movzx   eax, ax
0x180067e05  or      eax, 80070000h
0x180067e0a  test    eax, eax
0x180067e0c  js      short loc_180067E39
0x180067e0e  mov     rcx, [rsp+78h+String]; StringBinding
0x180067e13  lea     rdx, [rbx+8]; Binding
0x180067e17  call    cs:__imp_RpcBindingFromStringBindingW
0x180067e1d  mov     ebx, eax
0x180067e1f  test    eax, eax
0x180067e21  jle     short loc_180067E2C
0x180067e23  movzx   ebx, ax
0x180067e26  or      ebx, 80070000h
0x180067e2c  lea     rcx, [rsp+78h+String]; String
0x180067e31  call    cs:__imp_RpcStringFreeW
0x180067e37  mov     eax, ebx
0x180067e39  mov     rcx, [rsp+78h+var_18]
0x180067e3e  xor     rcx, rsp; StackCookie
0x180067e41  call    __security_check_cookie
0x180067e46  add     rsp, 70h
0x180067e4a  pop     rbx
0x180067e4b  retn
```
