# Microsoft::Diagnostics::UtcWrapperBase::Initialize(void)

- ea: `0x180104c20`
- end: `0x180104ce5`
- name: `?Initialize@UtcWrapperBase@Diagnostics@Microsoft@@QEAAJXZ`
- size: `197`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UtcWrapperBase *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800faad0`

## callees

- `0x180019080`
- `0x180104c20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180104c49`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180104c49`
- `RPCRT4!RpcStringBindingComposeW` at `0x180104c7e`
- `RPCRT4!RpcStringBindingComposeW` at `0x180104c7e`
- `RPCRT4!RpcStringFreeW` at `0x180104cc3`
- `RPCRT4!RpcStringFreeW` at `0x180104cc3`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180104ca3`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180104ca3`

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
0x180104c20  push    rbx
0x180104c22  sub     rsp, 70h
0x180104c26  mov     rax, cs:__security_cookie
0x180104c2d  xor     rax, rsp
0x180104c30  mov     [rsp+78h+var_18], rax
0x180104c35  mov     rbx, rcx
0x180104c38  lea     r8, aNcalrpc; "ncalrpc"
0x180104c3f  lea     rcx, [rsp+78h+ProtSeq]
0x180104c44  mov     edx, 14h
0x180104c49  call    cs:__imp__o_wcscpy_s
0x180104c50  nop     dword ptr [rax+rax+00h]
0x180104c55  lea     rax, [rsp+78h+String]
0x180104c5a  mov     [rsp+78h+String], 0
0x180104c63  mov     [rsp+78h+StringBinding], rax; StringBinding
0x180104c68  lea     rdx, [rsp+78h+ProtSeq]; ProtSeq
0x180104c6d  xor     r9d, r9d; Endpoint
0x180104c70  mov     [rsp+78h+Options], 0; Options
0x180104c79  xor     r8d, r8d; NetworkAddr
0x180104c7c  xor     ecx, ecx; ObjUuid
0x180104c7e  call    cs:__imp_RpcStringBindingComposeW
0x180104c85  nop     dword ptr [rax+rax+00h]
0x180104c8a  test    eax, eax
0x180104c8c  jle     short loc_180104C98
0x180104c8e  movzx   eax, ax
0x180104c91  or      eax, 80070000h
0x180104c96  test    eax, eax
0x180104c98  js      short loc_180104CD1
0x180104c9a  mov     rcx, [rsp+78h+String]; StringBinding
0x180104c9f  lea     rdx, [rbx+8]; Binding
0x180104ca3  call    cs:__imp_RpcBindingFromStringBindingW
0x180104caa  nop     dword ptr [rax+rax+00h]
0x180104caf  mov     ebx, eax
0x180104cb1  test    eax, eax
0x180104cb3  jle     short loc_180104CBE
0x180104cb5  movzx   ebx, ax
0x180104cb8  or      ebx, 80070000h
0x180104cbe  lea     rcx, [rsp+78h+String]; String
0x180104cc3  call    cs:__imp_RpcStringFreeW
0x180104cca  nop     dword ptr [rax+rax+00h]
0x180104ccf  mov     eax, ebx
0x180104cd1  mov     rcx, [rsp+78h+var_18]
0x180104cd6  xor     rcx, rsp; StackCookie
0x180104cd9  call    __security_check_cookie
0x180104cde  add     rsp, 70h
0x180104ce2  pop     rbx
0x180104ce3  retn
```
