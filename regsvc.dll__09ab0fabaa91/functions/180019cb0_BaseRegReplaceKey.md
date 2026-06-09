# BaseRegReplaceKey

- ea: `0x180019cb0`
- end: `0x180019d7a`
- name: `BaseRegReplaceKey`
- size: `202`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180007740`
- `0x180008042`
- `0x180019cb0`
- `0x18001c34c`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180019d1e`
- `RPCRT4!RpcRaiseException` at `0x180019d27`
- `RPCRT4!RpcRaiseException` at `0x180019d3c`
- `RPCRT4!RpcRaiseException` at `0x180019d1e`
- `RPCRT4!RpcRaiseException` at `0x180019d27`
- `RPCRT4!RpcRaiseException` at `0x180019d3c`
- `RPCRT4!RpcImpersonateClient` at `0x180019d30`
- `RPCRT4!RpcImpersonateClient` at `0x180019d30`
- `RPCRT4!RpcRevertToSelf` at `0x180019d56`
- `RPCRT4!RpcRevertToSelf` at `0x180019d56`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180019d03`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180019d03`

## pseudocode

```c
__int64 __fastcall BaseRegReplaceKey(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  ULONG v8; // ebx
  RPC_STATUS v9; // eax
  RPC_STATUS v10; // eax
  int RpcCallAttributes; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v13[36]; // [rsp+24h] [rbp-B4h] BYREF
  unsigned int v14; // [rsp+48h] [rbp-90h]

  if ( a1 )
  {
    memset_0(v13, 0, 0x74u);
    RpcCallAttributes = 3;
    v9 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
    if ( v9 != 1746 )
    {
      if ( v9 )
        RpcRaiseException(v9);
      if ( v14 < 6 )
        RpcRaiseException(5);
    }
    v10 = RpcImpersonateClient(0);
    if ( v10 )
      RpcRaiseException(v10);
    v8 = BaseRegReplaceKeyInternal(*a1, a2, a3, a4);
    RpcRevertToSelf();
  }
  else
  {
    return 87;
  }
  return v8;
}

```

## disassembly

```asm
0x180019cb0  push    rbx
0x180019cb2  push    rbp
0x180019cb3  push    rsi
0x180019cb4  push    rdi
0x180019cb5  sub     rsp, 0B8h
0x180019cbc  mov     rax, cs:__security_cookie
0x180019cc3  xor     rax, rsp
0x180019cc6  mov     [rsp+0D8h+var_38], rax
0x180019cce  mov     rbp, r9
0x180019cd1  mov     rsi, r8
0x180019cd4  mov     rdi, rdx
0x180019cd7  mov     rbx, rcx
0x180019cda  test    rcx, rcx
0x180019cdd  jnz     short loc_180019CE4
0x180019cdf  lea     ebx, [rcx+57h]
0x180019ce2  jmp     short loc_180019D5C
0x180019ce4  xor     edx, edx; Val
0x180019ce6  lea     rcx, [rsp+0D8h+var_B4]; void *
0x180019ceb  lea     r8d, [rdx+74h]; Size
0x180019cef  call    memset_0
0x180019cf4  lea     rdx, [rsp+0D8h+RpcCallAttributes]; RpcCallAttributes
0x180019cf9  mov     [rsp+0D8h+RpcCallAttributes], 3
0x180019d01  xor     ecx, ecx; ClientBinding
0x180019d03  call    cs:__imp_RpcServerInqCallAttributesW
0x180019d09  cmp     eax, 6D2h
0x180019d0e  jz      short loc_180019D2E
0x180019d10  test    eax, eax
0x180019d12  jnz     short loc_180019D25
0x180019d14  cmp     [rsp+0D8h+var_90], 6
0x180019d19  jnb     short loc_180019D2E
0x180019d1b  lea     ecx, [rax+5]; exception
0x180019d1e  call    cs:__imp_RpcRaiseException
0x180019d24  int     3; Trap to Debugger
0x180019d25  mov     ecx, eax; exception
0x180019d27  call    cs:__imp_RpcRaiseException
0x180019d2d  int     3; Trap to Debugger
0x180019d2e  xor     ecx, ecx; BindingHandle
0x180019d30  call    cs:__imp_RpcImpersonateClient
0x180019d36  test    eax, eax
0x180019d38  jz      short loc_180019D43
0x180019d3a  mov     ecx, eax; exception
0x180019d3c  call    cs:__imp_RpcRaiseException
0x180019d42  int     3; Trap to Debugger
0x180019d43  mov     rcx, [rbx]
0x180019d46  mov     r9, rbp
0x180019d49  mov     r8, rsi
0x180019d4c  mov     rdx, rdi
0x180019d4f  call    BaseRegReplaceKeyInternal
0x180019d54  mov     ebx, eax
0x180019d56  call    cs:__imp_RpcRevertToSelf
0x180019d5c  mov     eax, ebx
0x180019d5e  mov     rcx, [rsp+0D8h+var_38]
0x180019d66  xor     rcx, rsp; StackCookie
0x180019d69  call    __security_check_cookie
0x180019d6e  add     rsp, 0B8h
0x180019d75  pop     rdi
0x180019d76  pop     rsi
0x180019d77  pop     rbp
0x180019d78  pop     rbx
0x180019d79  retn
```
