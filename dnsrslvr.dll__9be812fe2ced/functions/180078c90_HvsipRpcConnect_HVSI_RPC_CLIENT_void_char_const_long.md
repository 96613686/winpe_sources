# HvsipRpcConnect(_HVSI_RPC_CLIENT *,void (*)(char const *,long))

- ea: `0x180078c90`
- end: `0x180078d3c`
- name: `?HvsipRpcConnect@@YAJPEAU_HVSI_RPC_CLIENT@@P6AXPEBDJ@Z@Z`
- size: `172`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding, void (__fastcall *)(const char *, __int64))`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800786f0`
- `0x180078830`
- `0x180078960`
- `0x180078ad8`

## callees

- `0x180078c90`
- `0x180089010`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180078d0a`
- `RPCRT4!RpcStringFreeW` at `0x180078d0a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180078cfd`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180078cfd`
- `RPCRT4!RpcStringBindingComposeW` at `0x180078cd9`
- `RPCRT4!RpcStringBindingComposeW` at `0x180078cd9`

## pseudocode

```c
__int64 __fastcall HvsipRpcConnect(RPC_BINDING_HANDLE *Binding, void (__fastcall *a2)(const char *, __int64))
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  const char *v7; // rcx
  RPC_WSTR StringBinding; // [rsp+40h] [rbp+8h] BYREF

  *((_BYTE *)Binding + 8) = 1;
  StringBinding = 0;
  v4 = RpcStringBindingComposeW(
         0,
         (RPC_WSTR)L"ncacn_hvsocket",
         (RPC_WSTR)L"parent",
         (RPC_WSTR)L"ABD802E8-FFCC-40D2-A5F1-F04B1D12CBC8",
         0,
         &StringBinding);
  v5 = v4;
  if ( v4 )
  {
    if ( a2 )
    {
      v6 = v4;
      v7 = "HvsipRpcConnect Error creating RPC binding";
LABEL_7:
      a2(v7, v6);
    }
  }
  else
  {
    v5 = RpcBindingFromStringBindingW(StringBinding, Binding);
    RpcStringFreeW(&StringBinding);
    if ( v5 && a2 )
    {
      v6 = v5;
      v7 = "HvsipRpcConnect Error creating an RPC server binding ";
      goto LABEL_7;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180078c90  mov     r11, rsp
0x180078c93  mov     [r11+10h], rbx
0x180078c97  mov     [r11+18h], rsi
0x180078c9b  push    rdi
0x180078c9c  sub     rsp, 30h
0x180078ca0  lea     rax, [r11+8]
0x180078ca4  mov     byte ptr [rcx+8], 1
0x180078ca8  mov     rdi, rdx
0x180078cab  mov     [r11-10h], rax
0x180078caf  mov     rsi, rcx
0x180078cb2  mov     qword ptr [r11-18h], 0
0x180078cba  lea     r9, aAbd802e8Ffcc40; "ABD802E8-FFCC-40D2-A5F1-F04B1D12CBC8"
0x180078cc1  mov     qword ptr [r11+8], 0
0x180078cc9  lea     r8, NetworkAddr; "parent"
0x180078cd0  xor     ecx, ecx; ObjUuid
0x180078cd2  lea     rdx, ProtSeq; "ncacn_hvsocket"
0x180078cd9  call    cs:__imp_RpcStringBindingComposeW
0x180078cdf  mov     ebx, eax
0x180078ce1  test    eax, eax
0x180078ce3  jz      short loc_180078CF5
0x180078ce5  test    rdi, rdi
0x180078ce8  jz      short loc_180078D2A
0x180078cea  mov     edx, eax
0x180078cec  lea     rcx, aHvsiprpcconnec_0; "HvsipRpcConnect Error creating RPC bind"...
0x180078cf3  jmp     short loc_180078D22
0x180078cf5  mov     rcx, [rsp+38h+StringBinding]; StringBinding
0x180078cfa  mov     rdx, rsi; Binding
0x180078cfd  call    cs:__imp_RpcBindingFromStringBindingW
0x180078d03  lea     rcx, [rsp+38h+StringBinding]; String
0x180078d08  mov     ebx, eax
0x180078d0a  call    cs:__imp_RpcStringFreeW
0x180078d10  test    ebx, ebx
0x180078d12  jz      short loc_180078D2A
0x180078d14  test    rdi, rdi
0x180078d17  jz      short loc_180078D2A
0x180078d19  mov     edx, ebx
0x180078d1b  lea     rcx, aHvsiprpcconnec; "HvsipRpcConnect Error creating an RPC s"...
0x180078d22  mov     rax, rdi
0x180078d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078d2a  mov     rsi, [rsp+38h+arg_10]
0x180078d2f  mov     eax, ebx
0x180078d31  mov     rbx, [rsp+38h+arg_8]
0x180078d36  add     rsp, 30h
0x180078d3a  pop     rdi
0x180078d3b  retn
```
