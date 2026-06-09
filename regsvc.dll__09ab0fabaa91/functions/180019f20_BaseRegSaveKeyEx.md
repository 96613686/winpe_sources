# BaseRegSaveKeyEx

- ea: `0x180019f20`
- end: `0x180019fea`
- name: `BaseRegSaveKeyEx`
- size: `202`
- prototype: `__int64 __fastcall(HANDLE *, __int16 *, __int64, ULONG)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180007740`
- `0x180008042`
- `0x180019f20`
- `0x18001ce28`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180019f8e`
- `RPCRT4!RpcRaiseException` at `0x180019f97`
- `RPCRT4!RpcRaiseException` at `0x180019fac`
- `RPCRT4!RpcRaiseException` at `0x180019f8e`
- `RPCRT4!RpcRaiseException` at `0x180019f97`
- `RPCRT4!RpcRaiseException` at `0x180019fac`
- `RPCRT4!RpcImpersonateClient` at `0x180019fa0`
- `RPCRT4!RpcImpersonateClient` at `0x180019fa0`
- `RPCRT4!RpcRevertToSelf` at `0x180019fc6`
- `RPCRT4!RpcRevertToSelf` at `0x180019fc6`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180019f73`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180019f73`

## pseudocode

```c
__int64 __fastcall BaseRegSaveKeyEx(HANDLE *a1, __int16 *a2, __int64 a3, ULONG a4)
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
    v8 = BaseRegSaveKeyExInternal(*a1, a2, a3, a4);
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
0x180019f20  push    rbx
0x180019f22  push    rbp
0x180019f23  push    rsi
0x180019f24  push    rdi
0x180019f25  sub     rsp, 0B8h
0x180019f2c  mov     rax, cs:__security_cookie
0x180019f33  xor     rax, rsp
0x180019f36  mov     [rsp+0D8h+var_38], rax
0x180019f3e  mov     ebp, r9d
0x180019f41  mov     rsi, r8
0x180019f44  mov     rdi, rdx
0x180019f47  mov     rbx, rcx
0x180019f4a  test    rcx, rcx
0x180019f4d  jnz     short loc_180019F54
0x180019f4f  lea     ebx, [rcx+57h]
0x180019f52  jmp     short loc_180019FCC
0x180019f54  xor     edx, edx; Val
0x180019f56  lea     rcx, [rsp+0D8h+var_B4]; void *
0x180019f5b  lea     r8d, [rdx+74h]; Size
0x180019f5f  call    memset_0
0x180019f64  lea     rdx, [rsp+0D8h+RpcCallAttributes]; RpcCallAttributes
0x180019f69  mov     [rsp+0D8h+RpcCallAttributes], 3
0x180019f71  xor     ecx, ecx; ClientBinding
0x180019f73  call    cs:__imp_RpcServerInqCallAttributesW
0x180019f79  cmp     eax, 6D2h
0x180019f7e  jz      short loc_180019F9E
0x180019f80  test    eax, eax
0x180019f82  jnz     short loc_180019F95
0x180019f84  cmp     [rsp+0D8h+var_90], 6
0x180019f89  jnb     short loc_180019F9E
0x180019f8b  lea     ecx, [rax+5]; exception
0x180019f8e  call    cs:__imp_RpcRaiseException
0x180019f94  int     3; Trap to Debugger
0x180019f95  mov     ecx, eax; exception
0x180019f97  call    cs:__imp_RpcRaiseException
0x180019f9d  int     3; Trap to Debugger
0x180019f9e  xor     ecx, ecx; BindingHandle
0x180019fa0  call    cs:__imp_RpcImpersonateClient
0x180019fa6  test    eax, eax
0x180019fa8  jz      short loc_180019FB3
0x180019faa  mov     ecx, eax; exception
0x180019fac  call    cs:__imp_RpcRaiseException
0x180019fb2  int     3; Trap to Debugger
0x180019fb3  mov     rcx, [rbx]; KeyHandle
0x180019fb6  mov     r9d, ebp
0x180019fb9  mov     r8, rsi
0x180019fbc  mov     rdx, rdi
0x180019fbf  call    BaseRegSaveKeyExInternal
0x180019fc4  mov     ebx, eax
0x180019fc6  call    cs:__imp_RpcRevertToSelf
0x180019fcc  mov     eax, ebx
0x180019fce  mov     rcx, [rsp+0D8h+var_38]
0x180019fd6  xor     rcx, rsp; StackCookie
0x180019fd9  call    __security_check_cookie
0x180019fde  add     rsp, 0B8h
0x180019fe5  pop     rdi
0x180019fe6  pop     rsi
0x180019fe7  pop     rbp
0x180019fe8  pop     rbx
0x180019fe9  retn
```
