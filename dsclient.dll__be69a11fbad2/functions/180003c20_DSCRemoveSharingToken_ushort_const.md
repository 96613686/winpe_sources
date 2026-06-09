# DSCRemoveSharingToken(ushort const *)

- ea: `0x180003c20`
- end: `0x180003cc1`
- name: `?DSCRemoveSharingToken@@YAJPEBG@Z`
- size: `161`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003460`

## callees

- `0x180001cf0`
- `0x180002220`
- `0x180003c20`
- `0x180006d94`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x180009df5`
- `RPCRT4!I_RpcExceptionFilter` at `0x180009df5`
- `RPCRT4!NdrClientCall3` at `0x180003c6c`
- `RPCRT4!NdrClientCall3` at `0x180003c6c`

## pseudocode

```c
__int64 __fastcall DSCRemoveSharingToken(const unsigned __int16 *a1)
{
  RPC_BINDING_HANDLE *v2; // rbx
  __int64 result; // rax

  v2 = (RPC_BINDING_HANDLE *)tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::get();
  result = RpcBinding::Bind(v2);
  if ( (int)result >= 0 )
    return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 4u, 0, *v2, a1).Simple;
  return result;
}

```

## disassembly

```asm
0x180003c20  mov     [rsp+arg_0], rcx
0x180003c25  push    rbx
0x180003c26  push    rdi
0x180003c27  sub     rsp, 48h
0x180003c2b  mov     rdi, rcx
0x180003c2e  call    ?get@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAAAEAVAutoRpcBinding@@XZ; tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::get(void)
0x180003c33  mov     rbx, rax
0x180003c36  mov     [rsp+58h+var_28], rax
0x180003c3b  mov     rcx, rax; this
0x180003c3e  call    ?Bind@RpcBinding@@QEAAJXZ; RpcBinding::Bind(void)
0x180003c43  test    eax, eax
0x180003c45  js      short loc_180003CBA
0x180003c47  mov     [rsp+58h+arg_8], 0
0x180003c4c  nop
0x180003c4d  mov     [rsp+58h+arg_18], 0
0x180003c56  mov     [rsp+58h+var_38], rdi
0x180003c5b  mov     r9, [rbx]
0x180003c5e  xor     r8d, r8d; pReturnValue
0x180003c61  lea     edx, [r8+4]; nProcNum
0x180003c65  lea     rcx, pProxyInfo; pProxyInfo
0x180003c6c  call    cs:__imp_NdrClientCall3
0x180003c72  mov     [rsp+58h+arg_18], rax
0x180003c77  mov     [rsp+58h+arg_10], eax
0x180003c7b  jmp     short loc_180003CBA
0x180003c7d  test    eax, eax
0x180003c7f  jle     short loc_180003C89
0x180003c81  movzx   eax, ax
0x180003c84  or      eax, 80070000h
0x180003c89  mov     ecx, 8000FFFFh
0x180003c8e  test    eax, eax
0x180003c90  cmovns  eax, ecx
0x180003c93  cmp     [rsp+58h+arg_8], 0
0x180003c98  jnz     short loc_180003CBA
0x180003c9a  cmp     eax, 800706BFh
0x180003c9f  jnz     short loc_180003CBA
0x180003ca1  mov     rbx, [rsp+58h+var_28]
0x180003ca6  mov     rcx, rbx; this
0x180003ca9  call    ?Rebind@RpcBinding@@QEAAJXZ; RpcBinding::Rebind(void)
0x180003cae  mov     [rsp+58h+arg_8], 1
0x180003cb3  mov     rdi, [rsp+58h+arg_0]
0x180003cb8  jmp     short loc_180003C4C
0x180003cba  add     rsp, 48h
0x180003cbe  pop     rdi
0x180003cbf  pop     rbx
0x180003cc0  retn
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
