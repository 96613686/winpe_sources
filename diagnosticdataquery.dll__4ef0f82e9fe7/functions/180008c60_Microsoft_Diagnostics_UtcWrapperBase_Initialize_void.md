# Microsoft::Diagnostics::UtcWrapperBase::Initialize(void)

- ea: `0x180008c60`
- end: `0x180008d0c`
- name: `?Initialize@UtcWrapperBase@Diagnostics@Microsoft@@QEAAJXZ`
- size: `172`
- prototype: `int __fastcall(RPC_BINDING_HANDLE *this)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008d20`
- `0x180008e00`
- `0x180008ed0`
- `0x180008fa0`
- `0x180009370`
- `0x1800094c0`
- `0x180009680`
- `0x1800097b0`
- `0x1800098f0`
- `0x180009a20`
- `0x180009b50`
- `0x180009c70`
- `0x180009d70`
- `0x180009e60`
- `0x180009f60`
- `0x18000a0f0`
- `0x18000a1d0`
- `0x18000a2b0`
- `0x18000a390`
- `0x18000a4b0`
- `0x18000a5b0`
- `0x18000a6c0`

## callees

- `0x180001500`
- `0x180008c60`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x180008c89`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x180008c89`
- `RPCRT4!RpcStringBindingComposeW` at `0x180008cb8`
- `RPCRT4!RpcStringBindingComposeW` at `0x180008cb8`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180008cd7`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180008cd7`
- `RPCRT4!RpcStringFreeW` at `0x180008cf1`
- `RPCRT4!RpcStringFreeW` at `0x180008cf1`

## pseudocode

```c
int __fastcall Microsoft::Diagnostics::UtcWrapperBase::Initialize(RPC_BINDING_HANDLE *this)
{
  int result; // eax
  bool v3; // sf
  RPC_STATUS v4; // eax
  unsigned int v5; // ebx
  RPC_WSTR String; // [rsp+30h] [rbp-48h] BYREF
  wchar_t Destination[20]; // [rsp+38h] [rbp-40h] BYREF

  wcscpy_s(Destination, 0x14u, L"ncalrpc");
  String = 0;
  result = RpcStringBindingComposeW(0, Destination, 0, 0, 0, &String);
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
0x180008c60  push    rbx
0x180008c62  sub     rsp, 70h
0x180008c66  mov     rax, cs:__security_cookie
0x180008c6d  xor     rax, rsp
0x180008c70  mov     [rsp+78h+var_18], rax
0x180008c75  mov     rbx, rcx
0x180008c78  lea     r8, aNcalrpc; "ncalrpc"
0x180008c7f  lea     rcx, [rsp+78h+Destination]; Destination
0x180008c84  mov     edx, 14h; SizeInWords
0x180008c89  call    cs:__imp_wcscpy_s
0x180008c8f  lea     rax, [rsp+78h+String]
0x180008c94  mov     [rsp+78h+String], 0
0x180008c9d  mov     [rsp+78h+StringBinding], rax; StringBinding
0x180008ca2  lea     rdx, [rsp+78h+Destination]; ProtSeq
0x180008ca7  xor     r9d, r9d; Endpoint
0x180008caa  mov     [rsp+78h+Options], 0; Options
0x180008cb3  xor     r8d, r8d; NetworkAddr
0x180008cb6  xor     ecx, ecx; ObjUuid
0x180008cb8  call    cs:__imp_RpcStringBindingComposeW
0x180008cbe  test    eax, eax
0x180008cc0  jle     short loc_180008CCC
0x180008cc2  movzx   eax, ax
0x180008cc5  or      eax, 80070000h
0x180008cca  test    eax, eax
0x180008ccc  js      short loc_180008CF9
0x180008cce  mov     rcx, [rsp+78h+String]; StringBinding
0x180008cd3  lea     rdx, [rbx+8]; Binding
0x180008cd7  call    cs:__imp_RpcBindingFromStringBindingW
0x180008cdd  mov     ebx, eax
0x180008cdf  test    eax, eax
0x180008ce1  jle     short loc_180008CEC
0x180008ce3  movzx   ebx, ax
0x180008ce6  or      ebx, 80070000h
0x180008cec  lea     rcx, [rsp+78h+String]; String
0x180008cf1  call    cs:__imp_RpcStringFreeW
0x180008cf7  mov     eax, ebx
0x180008cf9  mov     rcx, [rsp+78h+var_18]
0x180008cfe  xor     rcx, rsp; StackCookie
0x180008d01  call    __security_check_cookie
0x180008d06  add     rsp, 70h
0x180008d0a  pop     rbx
0x180008d0b  retn
```
