# BaseRegDeleteKey

- ea: `0x1800194e0`
- end: `0x1800195aa`
- name: `BaseRegDeleteKey`
- size: `202`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180007740`
- `0x180008042`
- `0x1800194e0`
- `0x18001c648`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180019549`
- `RPCRT4!RpcRaiseException` at `0x180019552`
- `RPCRT4!RpcRaiseException` at `0x180019567`
- `RPCRT4!RpcRaiseException` at `0x180019549`
- `RPCRT4!RpcRaiseException` at `0x180019552`
- `RPCRT4!RpcRaiseException` at `0x180019567`
- `RPCRT4!RpcImpersonateClient` at `0x18001955b`
- `RPCRT4!RpcImpersonateClient` at `0x18001955b`
- `RPCRT4!RpcRevertToSelf` at `0x180019581`
- `RPCRT4!RpcRevertToSelf` at `0x180019581`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001952e`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001952e`

## pseudocode

```c
__int64 __fastcall BaseRegDeleteKey(_QWORD *a1, __int64 a2)
{
  unsigned int v4; // ebx
  RPC_STATUS v5; // eax
  RPC_STATUS v6; // eax
  int RpcCallAttributes; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v9[36]; // [rsp+34h] [rbp-94h] BYREF
  unsigned int v10; // [rsp+58h] [rbp-70h]

  if ( a1 )
  {
    memset_0(v9, 0, 0x74u);
    RpcCallAttributes = 3;
    v5 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
    if ( v5 != 1746 )
    {
      if ( v5 )
        RpcRaiseException(v5);
      if ( v10 < 6 )
        RpcRaiseException(5);
    }
    v6 = RpcImpersonateClient(0);
    if ( v6 )
      RpcRaiseException(v6);
    v4 = BaseRegDeleteKeyExInternal(*a1, a2, 0, 0);
    RpcRevertToSelf();
  }
  else
  {
    return 87;
  }
  return v4;
}

```

## disassembly

```asm
0x1800194e0  mov     [rsp+arg_10], rbx
0x1800194e5  push    rdi
0x1800194e6  sub     rsp, 0C0h
0x1800194ed  mov     rax, cs:__security_cookie
0x1800194f4  xor     rax, rsp
0x1800194f7  mov     [rsp+0C8h+var_18], rax
0x1800194ff  mov     rdi, rdx
0x180019502  mov     rbx, rcx
0x180019505  test    rcx, rcx
0x180019508  jnz     short loc_18001950F
0x18001950a  lea     ebx, [rcx+57h]
0x18001950d  jmp     short loc_180019587
0x18001950f  xor     edx, edx; Val
0x180019511  lea     rcx, [rsp+0C8h+var_94]; void *
0x180019516  lea     r8d, [rdx+74h]; Size
0x18001951a  call    memset_0
0x18001951f  lea     rdx, [rsp+0C8h+RpcCallAttributes]; RpcCallAttributes
0x180019524  mov     [rsp+0C8h+RpcCallAttributes], 3
0x18001952c  xor     ecx, ecx; ClientBinding
0x18001952e  call    cs:__imp_RpcServerInqCallAttributesW
0x180019534  cmp     eax, 6D2h
0x180019539  jz      short loc_180019559
0x18001953b  test    eax, eax
0x18001953d  jnz     short loc_180019550
0x18001953f  cmp     [rsp+0C8h+var_70], 6
0x180019544  jnb     short loc_180019559
0x180019546  lea     ecx, [rax+5]; exception
0x180019549  call    cs:__imp_RpcRaiseException
0x18001954f  int     3; Trap to Debugger
0x180019550  mov     ecx, eax; exception
0x180019552  call    cs:__imp_RpcRaiseException
0x180019558  int     3; Trap to Debugger
0x180019559  xor     ecx, ecx; BindingHandle
0x18001955b  call    cs:__imp_RpcImpersonateClient
0x180019561  test    eax, eax
0x180019563  jz      short loc_18001956E
0x180019565  mov     ecx, eax; exception
0x180019567  call    cs:__imp_RpcRaiseException
0x18001956d  int     3; Trap to Debugger
0x18001956e  mov     rcx, [rbx]
0x180019571  xor     r9d, r9d
0x180019574  xor     r8d, r8d
0x180019577  mov     rdx, rdi
0x18001957a  call    BaseRegDeleteKeyExInternal
0x18001957f  mov     ebx, eax
0x180019581  call    cs:__imp_RpcRevertToSelf
0x180019587  mov     eax, ebx
0x180019589  mov     rcx, [rsp+0C8h+var_18]
0x180019591  xor     rcx, rsp; StackCookie
0x180019594  call    __security_check_cookie
0x180019599  mov     rbx, [rsp+0C8h+arg_10]
0x1800195a1  add     rsp, 0C0h
0x1800195a8  pop     rdi
0x1800195a9  retn
```
