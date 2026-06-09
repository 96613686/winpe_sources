# DSCCreateSharedFileToken(ushort const *,_DS_SHARE_ACCESS_CONTROL const *,_DS_TOKEN_LIFETIME_TYPE,_DS_TOKEN_USAGE_TYPE,ushort * *)

- ea: `0x180001be0`
- end: `0x180001cdb`
- name: `?DSCCreateSharedFileToken@@YAJPEBGPEBU_DS_SHARE_ACCESS_CONTROL@@W4_DS_TOKEN_LIFETIME_TYPE@@W4_DS_TOKEN_USAGE_TYPE@@PEAPEAG@Z`
- size: `251`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, int, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001810`

## callees

- `0x180001be0`
- `0x180001cf0`
- `0x180002220`
- `0x180006d94`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x180009afe`
- `RPCRT4!I_RpcExceptionFilter` at `0x180009afe`
- `RPCRT4!NdrClientCall3` at `0x180001c65`
- `RPCRT4!NdrClientCall3` at `0x180001c65`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall DSCCreateSharedFileToken(__int64 a1, __int64 a2, int a3, int a4, __int64 a5)
{
  RpcBinding *v9; // rbx
  CLIENT_CALL_RETURN result; // rax
  int v11; // [rsp+30h] [rbp-68h]
  int v12; // [rsp+38h] [rbp-60h]

  v9 = (RpcBinding *)tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::get();
  result.Simple = RpcBinding::Bind(v9);
  if ( SLODWORD(result.Simple) >= 0 )
  {
    v12 = a4;
    v11 = a3;
    return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, *(_QWORD *)v9, a1, a2, v11, v12, a5);
  }
  return result;
}

```

## disassembly

```asm
0x180001be0  mov     [rsp+arg_18], r9d
0x180001be5  mov     [rsp+arg_10], r8d
0x180001bea  mov     [rsp+arg_8], rdx
0x180001bef  mov     [rsp+arg_0], rcx
0x180001bf4  push    rbx
0x180001bf5  push    rsi
0x180001bf6  push    rdi
0x180001bf7  push    r14
0x180001bf9  push    r15
0x180001bfb  sub     rsp, 70h
0x180001bff  mov     edi, r9d
0x180001c02  mov     esi, r8d
0x180001c05  mov     r14, rdx
0x180001c08  mov     r15, rcx
0x180001c0b  call    ?get@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAAAEAVAutoRpcBinding@@XZ; tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::get(void)
0x180001c10  mov     rbx, rax
0x180001c13  mov     [rsp+98h+var_38], rax
0x180001c18  mov     rcx, rax; this
0x180001c1b  call    ?Bind@RpcBinding@@QEAAJXZ; RpcBinding::Bind(void)
0x180001c20  test    eax, eax
0x180001c22  js      loc_180001CCF
0x180001c28  mov     [rsp+98h+var_48], 0
0x180001c2d  nop
0x180001c2e  mov     [rsp+98h+var_40], 0
0x180001c37  mov     rax, [rsp+98h+arg_20]
0x180001c3f  mov     [rsp+98h+var_58], rax
0x180001c44  mov     [rsp+98h+var_60], edi
0x180001c48  mov     [rsp+98h+var_68], esi
0x180001c4c  mov     [rsp+98h+var_70], r14
0x180001c51  mov     [rsp+98h+var_78], r15
0x180001c56  mov     r9, [rbx]
0x180001c59  xor     r8d, r8d; pReturnValue
0x180001c5c  xor     edx, edx; nProcNum
0x180001c5e  lea     rcx, pProxyInfo; pProxyInfo
0x180001c65  call    cs:__imp_NdrClientCall3
0x180001c6b  mov     [rsp+98h+var_40], rax
0x180001c70  mov     [rsp+98h+var_44], eax
0x180001c74  jmp     short loc_180001CCF
0x180001c76  test    eax, eax
0x180001c78  jle     short loc_180001C82
0x180001c7a  movzx   eax, ax
0x180001c7d  or      eax, 80070000h
0x180001c82  mov     ecx, 8000FFFFh
0x180001c87  test    eax, eax
0x180001c89  cmovns  eax, ecx
0x180001c8c  cmp     [rsp+98h+var_48], 0
0x180001c91  jnz     short loc_180001CCF
0x180001c93  cmp     eax, 800706BFh
0x180001c98  jnz     short loc_180001CCF
0x180001c9a  mov     rbx, [rsp+98h+var_38]
0x180001c9f  mov     rcx, rbx; this
0x180001ca2  call    ?Rebind@RpcBinding@@QEAAJXZ; RpcBinding::Rebind(void)
0x180001ca7  mov     [rsp+98h+var_48], 1
0x180001cac  mov     edi, [rsp+98h+arg_18]
0x180001cb3  mov     esi, [rsp+98h+arg_10]
0x180001cba  mov     r14, [rsp+98h+arg_8]
0x180001cc2  mov     r15, [rsp+98h+arg_0]
0x180001cca  jmp     loc_180001C2D
0x180001ccf  add     rsp, 70h
0x180001cd3  pop     r15
0x180001cd5  pop     r14
0x180001cd7  pop     rdi
0x180001cd8  pop     rsi
0x180001cd9  pop     rbx
0x180001cda  retn
0x180009af0  push    rbp
0x180009af2  sub     rsp, 50h
0x180009af6  mov     rbp, rdx
0x180009af9  mov     rcx, [rcx]
0x180009afc  mov     ecx, [rcx]; ExceptionCode
0x180009afe  call    cs:__imp_I_RpcExceptionFilter
0x180009b04  nop
0x180009b05  add     rsp, 50h
0x180009b09  pop     rbp
0x180009b0a  retn
```
