# BaseRegQueryValue

- ea: `0x180019bb0`
- end: `0x180019c9f`
- name: `BaseRegQueryValue`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180007740`
- `0x180008042`
- `0x180019bb0`
- `0x18001bedc`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180019c35`
- `RPCRT4!RpcRaiseException` at `0x180019c3e`
- `RPCRT4!RpcRaiseException` at `0x180019c53`
- `RPCRT4!RpcRaiseException` at `0x180019c35`
- `RPCRT4!RpcRaiseException` at `0x180019c3e`
- `RPCRT4!RpcRaiseException` at `0x180019c53`
- `RPCRT4!RpcImpersonateClient` at `0x180019c47`
- `RPCRT4!RpcImpersonateClient` at `0x180019c47`
- `RPCRT4!RpcRevertToSelf` at `0x180019c77`
- `RPCRT4!RpcRevertToSelf` at `0x180019c77`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180019c1a`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180019c1a`

## pseudocode

```c
__int64 __fastcall BaseRegQueryValue(
        HKEY *a1,
        struct _UNICODE_STRING *a2,
        unsigned int *a3,
        unsigned __int8 *a4,
        unsigned int *a5,
        unsigned int *a6)
{
  unsigned int ValueInternal; // ebx
  RPC_STATUS v11; // eax
  RPC_STATUS v12; // eax
  int RpcCallAttributes; // [rsp+30h] [rbp-C8h] BYREF
  _BYTE v15[36]; // [rsp+34h] [rbp-C4h] BYREF
  unsigned int v16; // [rsp+58h] [rbp-A0h]

  if ( a1 )
  {
    memset_0(v15, 0, 0x74u);
    RpcCallAttributes = 3;
    v11 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
    if ( v11 != 1746 )
    {
      if ( v11 )
        RpcRaiseException(v11);
      if ( v16 < 6 )
        RpcRaiseException(5);
    }
    v12 = RpcImpersonateClient(0);
    if ( v12 )
      RpcRaiseException(v12);
    ValueInternal = BaseRegQueryValueInternal(*a1, a2, a3, a4, a5, a6);
    RpcRevertToSelf();
  }
  else
  {
    return 87;
  }
  return ValueInternal;
}

```

## disassembly

```asm
0x180019bb0  push    rbx
0x180019bb2  push    rbp
0x180019bb3  push    rsi
0x180019bb4  push    rdi
0x180019bb5  push    r14
0x180019bb7  push    r15
0x180019bb9  sub     rsp, 0C8h
0x180019bc0  mov     rax, cs:__security_cookie
0x180019bc7  xor     rax, rsp
0x180019bca  mov     [rsp+0F8h+var_48], rax
0x180019bd2  mov     r14, [rsp+0F8h+arg_20]
0x180019bda  mov     rbp, r9
0x180019bdd  mov     r15, [rsp+0F8h+arg_28]
0x180019be5  mov     rsi, r8
0x180019be8  mov     rdi, rdx
0x180019beb  mov     rbx, rcx
0x180019bee  test    rcx, rcx
0x180019bf1  jnz     short loc_180019BFB
0x180019bf3  lea     ebx, [rcx+57h]
0x180019bf6  jmp     loc_180019C7D
0x180019bfb  xor     edx, edx; Val
0x180019bfd  lea     rcx, [rsp+0F8h+var_C4]; void *
0x180019c02  lea     r8d, [rdx+74h]; Size
0x180019c06  call    memset_0
0x180019c0b  lea     rdx, [rsp+0F8h+RpcCallAttributes]; RpcCallAttributes
0x180019c10  mov     [rsp+0F8h+RpcCallAttributes], 3
0x180019c18  xor     ecx, ecx; ClientBinding
0x180019c1a  call    cs:__imp_RpcServerInqCallAttributesW
0x180019c20  cmp     eax, 6D2h
0x180019c25  jz      short loc_180019C45
0x180019c27  test    eax, eax
0x180019c29  jnz     short loc_180019C3C
0x180019c2b  cmp     [rsp+0F8h+var_A0], 6
0x180019c30  jnb     short loc_180019C45
0x180019c32  lea     ecx, [rax+5]; exception
0x180019c35  call    cs:__imp_RpcRaiseException
0x180019c3b  int     3; Trap to Debugger
0x180019c3c  mov     ecx, eax; exception
0x180019c3e  call    cs:__imp_RpcRaiseException
0x180019c44  int     3; Trap to Debugger
0x180019c45  xor     ecx, ecx; BindingHandle
0x180019c47  call    cs:__imp_RpcImpersonateClient
0x180019c4d  test    eax, eax
0x180019c4f  jz      short loc_180019C5A
0x180019c51  mov     ecx, eax; exception
0x180019c53  call    cs:__imp_RpcRaiseException
0x180019c59  int     3; Trap to Debugger
0x180019c5a  mov     rcx, [rbx]; HKEY
0x180019c5d  mov     r9, rbp; unsigned __int8 *
0x180019c60  mov     [rsp+0F8h+var_D0], r15; unsigned int *
0x180019c65  mov     r8, rsi; unsigned int *
0x180019c68  mov     rdx, rdi; struct _UNICODE_STRING *
0x180019c6b  mov     [rsp+0F8h+var_D8], r14; unsigned int *
0x180019c70  call    BaseRegQueryValueInternal
0x180019c75  mov     ebx, eax
0x180019c77  call    cs:__imp_RpcRevertToSelf
0x180019c7d  mov     eax, ebx
0x180019c7f  mov     rcx, [rsp+0F8h+var_48]
0x180019c87  xor     rcx, rsp; StackCookie
0x180019c8a  call    __security_check_cookie
0x180019c8f  add     rsp, 0C8h
0x180019c96  pop     r15
0x180019c98  pop     r14
0x180019c9a  pop     rdi
0x180019c9b  pop     rsi
0x180019c9c  pop     rbp
0x180019c9d  pop     rbx
0x180019c9e  retn
```
