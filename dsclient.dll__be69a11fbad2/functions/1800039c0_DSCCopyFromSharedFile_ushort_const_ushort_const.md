# DSCCopyFromSharedFile(ushort const *,ushort const *)

- ea: `0x1800039c0`
- end: `0x180003a75`
- name: `?DSCCopyFromSharedFile@@YAJPEBG0@Z`
- size: `181`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800031d0`

## callees

- `0x180001cf0`
- `0x180002220`
- `0x1800039c0`
- `0x180006d94`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180003a1a`
- `RPCRT4!NdrClientCall3` at `0x180003a1a`

## pseudocode

```c
__int64 __fastcall DSCCopyFromSharedFile(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  RPC_BINDING_HANDLE *v4; // rbx
  __int64 result; // rax

  v4 = (RPC_BINDING_HANDLE *)tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::get();
  result = RpcBinding::Bind(v4);
  if ( (int)result >= 0 )
    return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 6u, 0, *v4, a1, a2, 0, v4).Simple;
  return result;
}

```

## disassembly

```asm
0x1800039c0  mov     [rsp+arg_8], rdx
0x1800039c5  mov     [rsp+arg_0], rcx
0x1800039ca  push    rbx
0x1800039cb  push    rsi
0x1800039cc  push    rdi
0x1800039cd  sub     rsp, 40h
0x1800039d1  mov     rdi, rdx
0x1800039d4  mov     rsi, rcx
0x1800039d7  call    ?get@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAAAEAVAutoRpcBinding@@XZ; tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::get(void)
0x1800039dc  mov     rbx, rax
0x1800039df  mov     [rsp+58h+var_20], rax
0x1800039e4  mov     rcx, rax; this
0x1800039e7  call    ?Bind@RpcBinding@@QEAAJXZ; RpcBinding::Bind(void)
0x1800039ec  test    eax, eax
0x1800039ee  js      short loc_180003A6D
0x1800039f0  mov     [rsp+58h+arg_10], 0
0x1800039f5  nop
0x1800039f6  mov     [rsp+58h+var_28], 0
0x1800039ff  mov     [rsp+58h+var_30], rdi
0x180003a04  mov     [rsp+58h+var_38], rsi
0x180003a09  mov     r9, [rbx]
0x180003a0c  xor     r8d, r8d; pReturnValue
0x180003a0f  lea     edx, [r8+6]; nProcNum
0x180003a13  lea     rcx, pProxyInfo; pProxyInfo
0x180003a1a  call    cs:__imp_NdrClientCall3
0x180003a20  mov     [rsp+58h+var_28], rax
0x180003a25  mov     [rsp+58h+arg_18], eax
0x180003a29  jmp     short loc_180003A6D
0x180003a2b  test    eax, eax
0x180003a2d  jle     short loc_180003A37
0x180003a2f  movzx   eax, ax
0x180003a32  or      eax, 80070000h
0x180003a37  mov     ecx, 8000FFFFh
0x180003a3c  test    eax, eax
0x180003a3e  cmovns  eax, ecx
0x180003a41  cmp     [rsp+58h+arg_10], 0
0x180003a46  jnz     short loc_180003A6D
0x180003a48  cmp     eax, 800706BFh
0x180003a4d  jnz     short loc_180003A6D
0x180003a4f  mov     rbx, [rsp+58h+var_20]
0x180003a54  mov     rcx, rbx; this
0x180003a57  call    ?Rebind@RpcBinding@@QEAAJXZ; RpcBinding::Rebind(void)
0x180003a5c  mov     [rsp+58h+arg_10], 1
0x180003a61  mov     rdi, [rsp+58h+arg_8]
0x180003a66  mov     rsi, [rsp+58h+arg_0]
0x180003a6b  jmp     short loc_1800039F5
0x180003a6d  add     rsp, 40h
0x180003a71  pop     rdi
0x180003a72  pop     rsi
0x180003a73  pop     rbx
0x180003a74  retn
0x180009de7  push    rbp
0x180009de9  sub     rsp, 30h
0x180009ded  mov     rbp, rdx
0x180009df0  mov     rcx, [rcx]
0x180009df3  mov     ecx, [rcx]; ExceptionCode
0x180009df5  call    cs:__imp_I_RpcExceptionFilter
0x180009dfb  nop
0x180009dfc  add     rsp, 30h
0x180009e00  pop     rbp
0x180009e01  retn
```
