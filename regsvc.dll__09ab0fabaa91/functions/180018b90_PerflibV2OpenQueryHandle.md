# PerflibV2OpenQueryHandle

- ea: `0x180018b90`
- end: `0x180018c76`
- name: `PerflibV2OpenQueryHandle`
- size: `230`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180007740`
- `0x180008042`
- `0x1800166cc`
- `0x180018b90`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180018c0d`
- `RPCRT4!RpcRaiseException` at `0x180018c16`
- `RPCRT4!RpcRaiseException` at `0x180018c2b`
- `RPCRT4!RpcRaiseException` at `0x180018c0d`
- `RPCRT4!RpcRaiseException` at `0x180018c16`
- `RPCRT4!RpcRaiseException` at `0x180018c2b`
- `RPCRT4!RpcImpersonateClient` at `0x180018c1f`
- `RPCRT4!RpcImpersonateClient` at `0x180018c1f`
- `RPCRT4!RpcRevertToSelf` at `0x180018c41`
- `RPCRT4!RpcRevertToSelf` at `0x180018c41`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180018bf2`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180018bf2`

## pseudocode

```c
__int64 __fastcall PerflibV2OpenQueryHandle(__int64 a1, unsigned __int16 *a2, _QWORD *a3)
{
  unsigned int Handle; // ebx
  RPC_STATUS v6; // eax
  RPC_STATUS v7; // eax
  int RpcCallAttributes; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v10[36]; // [rsp+34h] [rbp-94h] BYREF
  unsigned int v11; // [rsp+58h] [rbp-70h]

  if ( a3 )
  {
    *a3 = 0;
    memset_0(v10, 0, 0x74u);
    RpcCallAttributes = 3;
    v6 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
    if ( v6 != 1746 )
    {
      if ( v6 )
        RpcRaiseException(v6);
      if ( v11 < 6 )
        RpcRaiseException(5);
    }
    v7 = RpcImpersonateClient(0);
    if ( v7 )
      RpcRaiseException(v7);
    Handle = PerflibciOpenLocalQueryHandle(a2);
    RpcRevertToSelf();
    if ( !Handle )
      *a3 = 0;
  }
  else
  {
    return 87;
  }
  return Handle;
}

```

## disassembly

```asm
0x180018b90  mov     [rsp+arg_0], rbx
0x180018b95  push    rdi
0x180018b96  sub     rsp, 0C0h
0x180018b9d  mov     rax, cs:__security_cookie
0x180018ba4  xor     rax, rsp
0x180018ba7  mov     [rsp+0C8h+var_18], rax
0x180018baf  mov     [rsp+0C8h+var_A8], 0
0x180018bb8  mov     rdi, r8
0x180018bbb  mov     rbx, rdx
0x180018bbe  test    r8, r8
0x180018bc1  jnz     short loc_180018BCC
0x180018bc3  lea     ebx, [r8+57h]
0x180018bc7  jmp     loc_180018C53
0x180018bcc  xor     edx, edx; Val
0x180018bce  mov     qword ptr [r8], 0
0x180018bd5  lea     rcx, [rsp+0C8h+var_94]; void *
0x180018bda  lea     r8d, [rdx+74h]; Size
0x180018bde  call    memset_0
0x180018be3  lea     rdx, [rsp+0C8h+RpcCallAttributes]; RpcCallAttributes
0x180018be8  mov     [rsp+0C8h+RpcCallAttributes], 3
0x180018bf0  xor     ecx, ecx; ClientBinding
0x180018bf2  call    cs:__imp_RpcServerInqCallAttributesW
0x180018bf8  cmp     eax, 6D2h
0x180018bfd  jz      short loc_180018C1D
0x180018bff  test    eax, eax
0x180018c01  jnz     short loc_180018C14
0x180018c03  cmp     [rsp+0C8h+var_70], 6
0x180018c08  jnb     short loc_180018C1D
0x180018c0a  lea     ecx, [rax+5]; exception
0x180018c0d  call    cs:__imp_RpcRaiseException
0x180018c13  int     3; Trap to Debugger
0x180018c14  mov     ecx, eax; exception
0x180018c16  call    cs:__imp_RpcRaiseException
0x180018c1c  int     3; Trap to Debugger
0x180018c1d  xor     ecx, ecx; BindingHandle
0x180018c1f  call    cs:__imp_RpcImpersonateClient
0x180018c25  test    eax, eax
0x180018c27  jz      short loc_180018C32
0x180018c29  mov     ecx, eax; exception
0x180018c2b  call    cs:__imp_RpcRaiseException
0x180018c31  int     3; Trap to Debugger
0x180018c32  lea     r8, [rsp+0C8h+var_A8]
0x180018c37  mov     rcx, rbx; unsigned __int16 *
0x180018c3a  call    PerflibciOpenLocalQueryHandle
0x180018c3f  mov     ebx, eax
0x180018c41  call    cs:__imp_RpcRevertToSelf
0x180018c47  test    ebx, ebx
0x180018c49  jnz     short loc_180018C53
0x180018c4b  mov     rcx, [rsp+0C8h+var_A8]
0x180018c50  mov     [rdi], rcx
0x180018c53  mov     eax, ebx
0x180018c55  mov     rcx, [rsp+0C8h+var_18]
0x180018c5d  xor     rcx, rsp; StackCookie
0x180018c60  call    __security_check_cookie
0x180018c65  mov     rbx, [rsp+0C8h+arg_0]
0x180018c6d  add     rsp, 0C0h
0x180018c74  pop     rdi
0x180018c75  retn
```
