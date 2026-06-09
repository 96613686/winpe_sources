# DSCGetSharingTokenInformation(ushort const *,ushort * *,ushort * *,_DS_SHARE_PERMISSION *)

- ea: `0x180001400`
- end: `0x1800014f5`
- name: `?DSCGetSharingTokenInformation@@YAJPEBGPEAPEAG1PEAW4_DS_SHARE_PERMISSION@@@Z`
- size: `245`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, enum _DS_SHARE_PERMISSION *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000313c`

## callees

- `0x180001400`
- `0x180001cf0`
- `0x180002220`
- `0x180006d94`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x180009a6e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180009a6e`
- `RPCRT4!NdrClientCall3` at `0x18000147d`
- `RPCRT4!NdrClientCall3` at `0x18000147d`

## pseudocode

```c
__int64 __fastcall DSCGetSharingTokenInformation(
        const unsigned __int16 *a1,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        enum _DS_SHARE_PERMISSION *a4)
{
  RPC_BINDING_HANDLE *v8; // rbx
  __int64 result; // rax
  char v10; // [rsp+40h] [rbp-48h]

  v8 = (RPC_BINDING_HANDLE *)tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::get();
  result = RpcBinding::Bind(v8);
  if ( (int)result >= 0 )
  {
    v10 = 0;
    return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, *v8, a1, a2, a3, a4, v10, 0, v8).Simple;
  }
  return result;
}

```

## disassembly

```asm
0x180001400  mov     [rsp+arg_18], r9
0x180001405  mov     [rsp+arg_10], r8
0x18000140a  mov     [rsp+arg_8], rdx
0x18000140f  mov     [rsp+arg_0], rcx
0x180001414  push    rbx
0x180001415  push    rsi
0x180001416  push    rdi
0x180001417  push    r14
0x180001419  push    r15
0x18000141b  sub     rsp, 60h
0x18000141f  mov     rdi, r9
0x180001422  mov     rsi, r8
0x180001425  mov     r14, rdx
0x180001428  mov     r15, rcx
0x18000142b  call    ?get@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAAAEAVAutoRpcBinding@@XZ; tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::get(void)
0x180001430  mov     rbx, rax
0x180001433  mov     [rsp+88h+var_38], rax
0x180001438  mov     rcx, rax; this
0x18000143b  call    ?Bind@RpcBinding@@QEAAJXZ; RpcBinding::Bind(void)
0x180001440  test    eax, eax
0x180001442  js      loc_1800014E9
0x180001448  mov     [rsp+88h+var_48], 0
0x18000144d  nop
0x18000144e  mov     [rsp+88h+var_40], 0
0x180001457  mov     [rsp+88h+var_50], rdi
0x18000145c  mov     [rsp+88h+var_58], rsi
0x180001461  mov     [rsp+88h+var_60], r14
0x180001466  mov     [rsp+88h+var_68], r15
0x18000146b  mov     r9, [rbx]
0x18000146e  xor     r8d, r8d; pReturnValue
0x180001471  mov     edx, 2; nProcNum
0x180001476  lea     rcx, pProxyInfo; pProxyInfo
0x18000147d  call    cs:__imp_NdrClientCall3
0x180001483  mov     [rsp+88h+var_40], rax
0x180001488  mov     [rsp+88h+var_44], eax
0x18000148c  jmp     short loc_1800014E9
0x18000148e  test    eax, eax
0x180001490  jle     short loc_18000149A
0x180001492  movzx   eax, ax
0x180001495  or      eax, 80070000h
0x18000149a  mov     ecx, 8000FFFFh
0x18000149f  test    eax, eax
0x1800014a1  cmovns  eax, ecx
0x1800014a4  cmp     [rsp+88h+var_48], 0
0x1800014a9  jnz     short loc_1800014E9
0x1800014ab  cmp     eax, 800706BFh
0x1800014b0  jnz     short loc_1800014E9
0x1800014b2  mov     rbx, [rsp+88h+var_38]
0x1800014b7  mov     rcx, rbx; this
0x1800014ba  call    ?Rebind@RpcBinding@@QEAAJXZ; RpcBinding::Rebind(void)
0x1800014bf  mov     [rsp+88h+var_48], 1
0x1800014c4  mov     rdi, [rsp+88h+arg_18]
0x1800014cc  mov     rsi, [rsp+88h+arg_10]
0x1800014d4  mov     r14, [rsp+88h+arg_8]
0x1800014dc  mov     r15, [rsp+88h+arg_0]
0x1800014e4  jmp     loc_18000144D
0x1800014e9  add     rsp, 60h
0x1800014ed  pop     r15
0x1800014ef  pop     r14
0x1800014f1  pop     rdi
0x1800014f2  pop     rsi
0x1800014f3  pop     rbx
0x1800014f4  retn
0x180009a60  push    rbp
0x180009a62  sub     rsp, 40h
0x180009a66  mov     rbp, rdx
0x180009a69  mov     rcx, [rcx]
0x180009a6c  mov     ecx, [rcx]; ExceptionCode
0x180009a6e  call    cs:__imp_I_RpcExceptionFilter
0x180009a74  nop
0x180009a75  add     rsp, 40h
0x180009a79  pop     rbp
0x180009a7a  retn
```
