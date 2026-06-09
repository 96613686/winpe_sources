# SafeBaseRegQueryMultipleValues2

- ea: `0x18001b760`
- end: `0x18001b95d`
- name: `SafeBaseRegQueryMultipleValues2`
- size: `509`
- prototype: `__int64 __fastcall(HANDLE *, __int64, struct _KEY_VALUE_ENTRY *, ULONG, __int64, __int64, ULONG *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180007740`
- `0x180008042`
- `0x18001b760`
- `0x18001be20`
- `0x18001e431`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18001b8e5`
- `RPCRT4!RpcRaiseException` at `0x18001b8ee`
- `RPCRT4!RpcRaiseException` at `0x18001b903`
- `RPCRT4!RpcRaiseException` at `0x18001b8e5`
- `RPCRT4!RpcRaiseException` at `0x18001b8ee`
- `RPCRT4!RpcRaiseException` at `0x18001b903`
- `RPCRT4!RpcImpersonateClient` at `0x18001b8f7`
- `RPCRT4!RpcImpersonateClient` at `0x18001b8f7`
- `RPCRT4!RpcRevertToSelf` at `0x18001b92a`
- `RPCRT4!RpcRevertToSelf` at `0x18001b92a`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001b8ca`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001b8ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b820`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b84b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b820`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b84b`

## pseudocode

```c
__int64 __fastcall SafeBaseRegQueryMultipleValues2(
        HANDLE *a1,
        __int64 a2,
        struct _KEY_VALUE_ENTRY *a3,
        ULONG a4,
        __int64 a5,
        __int64 a6,
        ULONG *a7)
{
  ULONG i; // edx
  __int64 v12; // rax
  ULONG j; // ebp
  struct _UNICODE_STRING *v14; // rcx
  PUNICODE_STRING ValueName; // rdx
  unsigned int MultipleValues2Old; // ebx
  RPC_STATUS v17; // eax
  RPC_STATUS v18; // eax
  int RpcCallAttributes; // [rsp+40h] [rbp-D8h] BYREF
  _BYTE v21[36]; // [rsp+44h] [rbp-D4h] BYREF
  unsigned int v22; // [rsp+68h] [rbp-B0h]

  if ( a1 && a6 && a7 && (!a4 || a2) && a3 )
  {
    for ( i = 0; i < a4; ++i )
    {
      v12 = *(_QWORD *)(a2 + 24LL * i);
      if ( *(_WORD *)v12 && (!*(_QWORD *)(v12 + 8) || (*(_BYTE *)v12 & 1) != 0) )
        return 87;
    }
    for ( j = 0; j < a4; ++j )
    {
      v14 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, 0x10u);
      a3[j].ValueName = v14;
      if ( !v14 )
        return 14;
      *v14 = 0;
      a3[j].ValueName->Buffer = (PWSTR)LocalAlloc(0x40u, *(unsigned __int16 *)(*(_QWORD *)(a2 + 24LL * j) + 2LL));
      ValueName = a3[j].ValueName;
      if ( !ValueName->Buffer )
        return 14;
      ValueName->MaximumLength = *(_WORD *)(*(_QWORD *)(a2 + 24LL * j) + 2LL);
      a3[j].ValueName->Length = **(_WORD **)(a2 + 24LL * j);
      memcpy_0(
        a3[j].ValueName->Buffer,
        *(const void **)(*(_QWORD *)(a2 + 24LL * j) + 8LL),
        **(unsigned __int16 **)(a2 + 24LL * j));
    }
    memset_0(v21, 0, 0x74u);
    RpcCallAttributes = 3;
    v17 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
    if ( v17 != 1746 )
    {
      if ( v17 )
        RpcRaiseException(v17);
      if ( v22 < 6 )
        RpcRaiseException(5);
    }
    v18 = RpcImpersonateClient(0);
    if ( v18 )
      RpcRaiseException(v18);
    MultipleValues2Old = BaseRegQueryMultipleValues2Old(*a1, a3, a4, a6, a7);
    RpcRevertToSelf();
  }
  else
  {
    return 87;
  }
  return MultipleValues2Old;
}

```

## disassembly

```asm
0x18001b760  push    rbx
0x18001b762  push    rbp
0x18001b763  push    rsi
0x18001b764  push    rdi
0x18001b765  push    r12
0x18001b767  push    r13
0x18001b769  push    r14
0x18001b76b  push    r15
0x18001b76d  sub     rsp, 0D8h
0x18001b774  mov     rax, cs:__security_cookie
0x18001b77b  xor     rax, rsp
0x18001b77e  mov     [rsp+118h+var_58], rax
0x18001b786  mov     rsi, [rsp+118h+arg_20]
0x18001b78e  mov     ebx, r9d
0x18001b791  mov     r15, [rsp+118h+arg_28]
0x18001b799  mov     rdi, r8
0x18001b79c  mov     r12, [rsp+118h+arg_30]
0x18001b7a4  mov     r14, rdx
0x18001b7a7  mov     [rsp+118h+var_E8], rsi
0x18001b7ac  mov     r13, rcx
0x18001b7af  xor     esi, esi
0x18001b7b1  test    rcx, rcx
0x18001b7b4  jz      loc_18001B932
0x18001b7ba  test    r15, r15
0x18001b7bd  jz      loc_18001B932
0x18001b7c3  test    r12, r12
0x18001b7c6  jz      loc_18001B932
0x18001b7cc  test    ebx, ebx
0x18001b7ce  jz      short loc_18001B7D9
0x18001b7d0  test    rdx, rdx
0x18001b7d3  jz      loc_18001B932
0x18001b7d9  test    rdi, rdi
0x18001b7dc  jz      loc_18001B932
0x18001b7e2  mov     edx, esi
0x18001b7e4  cmp     edx, ebx
0x18001b7e6  jnb     short loc_18001B80E
0x18001b7e8  mov     eax, edx
0x18001b7ea  lea     rcx, [rax+rax*2]
0x18001b7ee  mov     rax, [r14+rcx*8]
0x18001b7f2  cmp     [rax], si
0x18001b7f5  jz      short loc_18001B80A
0x18001b7f7  cmp     [rax+8], rsi
0x18001b7fb  jz      loc_18001B932
0x18001b801  test    byte ptr [rax], 1
0x18001b804  jnz     loc_18001B932
0x18001b80a  inc     edx
0x18001b80c  jmp     short loc_18001B7E4
0x18001b80e  mov     ebp, esi
0x18001b810  cmp     ebp, ebx
0x18001b812  jnb     loc_18001B8AB
0x18001b818  mov     edx, 10h; uBytes
0x18001b81d  lea     ecx, [rdx+30h]; uFlags
0x18001b820  call    cs:__imp_LocalAlloc
0x18001b826  mov     rcx, rax
0x18001b829  mov     eax, ebp
0x18001b82b  lea     rsi, [rax+rax*2]
0x18001b82f  mov     [rdi+rsi*8], rcx
0x18001b833  test    rcx, rcx
0x18001b836  jz      short loc_18001B8A1
0x18001b838  xorps   xmm0, xmm0
0x18001b83b  movups  xmmword ptr [rcx], xmm0
0x18001b83e  mov     rax, [r14+rsi*8]
0x18001b842  mov     ecx, 40h ; '@'; uFlags
0x18001b847  movzx   edx, word ptr [rax+2]; uBytes
0x18001b84b  call    cs:__imp_LocalAlloc
0x18001b851  mov     rcx, rax
0x18001b854  mov     rax, [rdi+rsi*8]
0x18001b858  mov     [rax+8], rcx
0x18001b85c  mov     rdx, [rdi+rsi*8]
0x18001b860  cmp     qword ptr [rdx+8], 0
0x18001b865  jz      short loc_18001B8A1
0x18001b867  mov     rax, [r14+rsi*8]
0x18001b86b  movzx   ecx, word ptr [rax+2]
0x18001b86f  mov     [rdx+2], cx
0x18001b873  mov     rax, [r14+rsi*8]
0x18001b877  mov     rcx, [rdi+rsi*8]
0x18001b87b  movzx   eax, word ptr [rax]
0x18001b87e  mov     [rcx], ax
0x18001b881  mov     rdx, [r14+rsi*8]
0x18001b885  mov     rcx, [rdi+rsi*8]
0x18001b889  movzx   r8d, word ptr [rdx]; Size
0x18001b88d  mov     rdx, [rdx+8]; Src
0x18001b891  mov     rcx, [rcx+8]; void *
0x18001b895  call    memcpy_0
0x18001b89a  inc     ebp
0x18001b89c  jmp     loc_18001B810
0x18001b8a1  mov     ebx, 0Eh
0x18001b8a6  jmp     loc_18001B937
0x18001b8ab  xor     edx, edx; Val
0x18001b8ad  lea     rcx, [rsp+118h+var_D4]; void *
0x18001b8b2  lea     r8d, [rdx+74h]; Size
0x18001b8b6  call    memset_0
0x18001b8bb  lea     rdx, [rsp+118h+RpcCallAttributes]; RpcCallAttributes
0x18001b8c0  mov     [rsp+118h+RpcCallAttributes], 3
0x18001b8c8  xor     ecx, ecx; ClientBinding
0x18001b8ca  call    cs:__imp_RpcServerInqCallAttributesW
0x18001b8d0  cmp     eax, 6D2h
0x18001b8d5  jz      short loc_18001B8F5
0x18001b8d7  test    eax, eax
0x18001b8d9  jnz     short loc_18001B8EC
0x18001b8db  cmp     [rsp+118h+var_B0], 6
0x18001b8e0  jnb     short loc_18001B8F5
0x18001b8e2  lea     ecx, [rax+5]; exception
0x18001b8e5  call    cs:__imp_RpcRaiseException
0x18001b8eb  int     3; Trap to Debugger
0x18001b8ec  mov     ecx, eax; exception
0x18001b8ee  call    cs:__imp_RpcRaiseException
0x18001b8f4  int     3; Trap to Debugger
0x18001b8f5  xor     ecx, ecx; BindingHandle
0x18001b8f7  call    cs:__imp_RpcImpersonateClient
0x18001b8fd  test    eax, eax
0x18001b8ff  jz      short loc_18001B90A
0x18001b901  mov     ecx, eax; exception
0x18001b903  call    cs:__imp_RpcRaiseException
0x18001b909  int     3; Trap to Debugger
0x18001b90a  mov     r9, [rsp+118h+var_E8]
0x18001b90f  mov     r8d, ebx; EntryCount
0x18001b912  mov     rcx, [r13+0]; KeyHandle
0x18001b916  mov     rdx, rdi; ValueEntries
0x18001b919  mov     [rsp+118h+var_F0], r12; PULONG
0x18001b91e  mov     [rsp+118h+var_F8], r15; __int64
0x18001b923  call    BaseRegQueryMultipleValues2Old
0x18001b928  mov     ebx, eax
0x18001b92a  call    cs:__imp_RpcRevertToSelf
0x18001b930  jmp     short loc_18001B937
0x18001b932  mov     ebx, 57h ; 'W'
0x18001b937  mov     eax, ebx
0x18001b939  mov     rcx, [rsp+118h+var_58]
0x18001b941  xor     rcx, rsp; StackCookie
0x18001b944  call    __security_check_cookie
0x18001b949  add     rsp, 0D8h
0x18001b950  pop     r15
0x18001b952  pop     r14
0x18001b954  pop     r13
0x18001b956  pop     r12
0x18001b958  pop     rdi
0x18001b959  pop     rsi
0x18001b95a  pop     rbp
0x18001b95b  pop     rbx
0x18001b95c  retn
```
