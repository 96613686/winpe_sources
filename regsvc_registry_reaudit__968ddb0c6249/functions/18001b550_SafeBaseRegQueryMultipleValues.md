# SafeBaseRegQueryMultipleValues

- ea: `0x18001b550`
- end: `0x18001b74c`
- name: `SafeBaseRegQueryMultipleValues`
- size: `508`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180007740`
- `0x180008042`
- `0x18001b550`
- `0x18001be20`
- `0x18001e431`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18001b6c1`
- `RPCRT4!RpcRaiseException` at `0x18001b6ca`
- `RPCRT4!RpcRaiseException` at `0x18001b6df`
- `RPCRT4!RpcRaiseException` at `0x18001b6c1`
- `RPCRT4!RpcRaiseException` at `0x18001b6ca`
- `RPCRT4!RpcRaiseException` at `0x18001b6df`
- `RPCRT4!RpcImpersonateClient` at `0x18001b6d3`
- `RPCRT4!RpcImpersonateClient` at `0x18001b6d3`
- `RPCRT4!RpcRevertToSelf` at `0x18001b719`
- `RPCRT4!RpcRevertToSelf` at `0x18001b719`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001b6a4`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001b6a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b5fa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b625`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b5fa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b625`

## pseudocode

```c
__int64 __fastcall SafeBaseRegQueryMultipleValues(
        void **a1,
        __int64 a2,
        struct _KEY_VALUE_ENTRY *a3,
        ULONG a4,
        __int64 a5,
        ULONG *a6)
{
  ULONG i; // edx
  __int64 v11; // rax
  ULONG j; // ebp
  struct _UNICODE_STRING *v13; // rcx
  PUNICODE_STRING ValueName; // rdx
  unsigned int MultipleValues2Old; // ebx
  RPC_STATUS v16; // eax
  RPC_STATUS v17; // eax
  void *v18; // rcx
  ULONG v19; // eax
  ULONG v21[4]; // [rsp+30h] [rbp-E8h] BYREF
  int RpcCallAttributes; // [rsp+40h] [rbp-D8h] BYREF
  _BYTE v23[36]; // [rsp+44h] [rbp-D4h] BYREF
  unsigned int v24; // [rsp+68h] [rbp-B0h]

  if ( a1 && a6 && (!a4 || a2) && a3 )
  {
    for ( i = 0; i < a4; ++i )
    {
      v11 = *(_QWORD *)(a2 + 24LL * i);
      if ( *(_WORD *)v11 && (!*(_QWORD *)(v11 + 8) || (*(_BYTE *)v11 & 1) != 0) )
        return 87;
    }
    for ( j = 0; j < a4; ++j )
    {
      v13 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, 0x10u);
      a3[j].ValueName = v13;
      if ( !v13 )
        return 14;
      *v13 = 0;
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
    memset_0(v23, 0, 0x74u);
    RpcCallAttributes = 3;
    v16 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
    if ( v16 != 1746 )
    {
      if ( v16 )
        RpcRaiseException(v16);
      if ( v24 < 6 )
        RpcRaiseException(5);
    }
    v17 = RpcImpersonateClient(0);
    if ( v17 )
      RpcRaiseException(v17);
    v18 = *a1;
    v21[0] = 0;
    MultipleValues2Old = BaseRegQueryMultipleValues2Old(v18, a3, a4, (__int64)a6, v21);
    v19 = 0;
    if ( !MultipleValues2Old )
      v19 = v21[0];
    *a6 = v19;
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
0x18001b550  push    rbx
0x18001b552  push    rbp
0x18001b553  push    rsi
0x18001b554  push    rdi
0x18001b555  push    r12
0x18001b557  push    r13
0x18001b559  push    r14
0x18001b55b  push    r15
0x18001b55d  sub     rsp, 0D8h
0x18001b564  mov     rax, cs:__security_cookie
0x18001b56b  xor     rax, rsp
0x18001b56e  mov     [rsp+118h+var_58], rax
0x18001b576  mov     r13, [rsp+118h+arg_20]
0x18001b57e  xor     edi, edi
0x18001b580  mov     r15, [rsp+118h+arg_28]
0x18001b588  mov     ebx, r9d
0x18001b58b  mov     rsi, r8
0x18001b58e  mov     r14, rdx
0x18001b591  mov     r12, rcx
0x18001b594  test    rcx, rcx
0x18001b597  jz      loc_18001B721
0x18001b59d  test    r15, r15
0x18001b5a0  jz      loc_18001B721
0x18001b5a6  test    ebx, ebx
0x18001b5a8  jz      short loc_18001B5B3
0x18001b5aa  test    rdx, rdx
0x18001b5ad  jz      loc_18001B721
0x18001b5b3  test    rsi, rsi
0x18001b5b6  jz      loc_18001B721
0x18001b5bc  mov     edx, edi
0x18001b5be  cmp     edx, ebx
0x18001b5c0  jnb     short loc_18001B5E8
0x18001b5c2  mov     eax, edx
0x18001b5c4  lea     rcx, [rax+rax*2]
0x18001b5c8  mov     rax, [r14+rcx*8]
0x18001b5cc  cmp     [rax], di
0x18001b5cf  jz      short loc_18001B5E4
0x18001b5d1  cmp     [rax+8], rdi
0x18001b5d5  jz      loc_18001B721
0x18001b5db  test    byte ptr [rax], 1
0x18001b5de  jnz     loc_18001B721
0x18001b5e4  inc     edx
0x18001b5e6  jmp     short loc_18001B5BE
0x18001b5e8  mov     ebp, edi
0x18001b5ea  cmp     ebp, ebx
0x18001b5ec  jnb     loc_18001B685
0x18001b5f2  mov     edx, 10h; uBytes
0x18001b5f7  lea     ecx, [rdx+30h]; uFlags
0x18001b5fa  call    cs:__imp_LocalAlloc
0x18001b600  mov     rcx, rax
0x18001b603  mov     eax, ebp
0x18001b605  lea     rdi, [rax+rax*2]
0x18001b609  mov     [rsi+rdi*8], rcx
0x18001b60d  test    rcx, rcx
0x18001b610  jz      short loc_18001B67B
0x18001b612  xorps   xmm0, xmm0
0x18001b615  movups  xmmword ptr [rcx], xmm0
0x18001b618  mov     rax, [r14+rdi*8]
0x18001b61c  mov     ecx, 40h ; '@'; uFlags
0x18001b621  movzx   edx, word ptr [rax+2]; uBytes
0x18001b625  call    cs:__imp_LocalAlloc
0x18001b62b  mov     rcx, rax
0x18001b62e  mov     rax, [rsi+rdi*8]
0x18001b632  mov     [rax+8], rcx
0x18001b636  mov     rdx, [rsi+rdi*8]
0x18001b63a  cmp     qword ptr [rdx+8], 0
0x18001b63f  jz      short loc_18001B67B
0x18001b641  mov     rax, [r14+rdi*8]
0x18001b645  movzx   ecx, word ptr [rax+2]
0x18001b649  mov     [rdx+2], cx
0x18001b64d  mov     rax, [r14+rdi*8]
0x18001b651  mov     rcx, [rsi+rdi*8]
0x18001b655  movzx   eax, word ptr [rax]
0x18001b658  mov     [rcx], ax
0x18001b65b  mov     rdx, [r14+rdi*8]
0x18001b65f  mov     rcx, [rsi+rdi*8]
0x18001b663  movzx   r8d, word ptr [rdx]; Size
0x18001b667  mov     rdx, [rdx+8]; Src
0x18001b66b  mov     rcx, [rcx+8]; void *
0x18001b66f  call    memcpy_0
0x18001b674  inc     ebp
0x18001b676  jmp     loc_18001B5EA
0x18001b67b  mov     ebx, 0Eh
0x18001b680  jmp     loc_18001B726
0x18001b685  xor     edx, edx; Val
0x18001b687  lea     rcx, [rsp+118h+var_D4]; void *
0x18001b68c  lea     r8d, [rdx+74h]; Size
0x18001b690  call    memset_0
0x18001b695  lea     rdx, [rsp+118h+RpcCallAttributes]; RpcCallAttributes
0x18001b69a  mov     [rsp+118h+RpcCallAttributes], 3
0x18001b6a2  xor     ecx, ecx; ClientBinding
0x18001b6a4  call    cs:__imp_RpcServerInqCallAttributesW
0x18001b6aa  xor     edi, edi
0x18001b6ac  cmp     eax, 6D2h
0x18001b6b1  jz      short loc_18001B6D1
0x18001b6b3  test    eax, eax
0x18001b6b5  jnz     short loc_18001B6C8
0x18001b6b7  cmp     [rsp+118h+var_B0], 6
0x18001b6bc  jnb     short loc_18001B6D1
0x18001b6be  lea     ecx, [rdi+5]; exception
0x18001b6c1  call    cs:__imp_RpcRaiseException
0x18001b6c7  int     3; Trap to Debugger
0x18001b6c8  mov     ecx, eax; exception
0x18001b6ca  call    cs:__imp_RpcRaiseException
0x18001b6d0  int     3; Trap to Debugger
0x18001b6d1  xor     ecx, ecx; BindingHandle
0x18001b6d3  call    cs:__imp_RpcImpersonateClient
0x18001b6d9  test    eax, eax
0x18001b6db  jz      short loc_18001B6E6
0x18001b6dd  mov     ecx, eax; exception
0x18001b6df  call    cs:__imp_RpcRaiseException
0x18001b6e5  int     3; Trap to Debugger
0x18001b6e6  mov     rcx, [r12]; KeyHandle
0x18001b6ea  lea     rax, [rsp+118h+var_E8]
0x18001b6ef  mov     [rsp+118h+var_F0], rax; PULONG
0x18001b6f4  mov     r9, r13
0x18001b6f7  mov     r8d, ebx; EntryCount
0x18001b6fa  mov     [rsp+118h+var_F8], r15; __int64
0x18001b6ff  mov     rdx, rsi; ValueEntries
0x18001b702  mov     [rsp+118h+var_E8], edi
0x18001b706  call    BaseRegQueryMultipleValues2Old
0x18001b70b  mov     ebx, eax
0x18001b70d  mov     eax, edi
0x18001b70f  test    ebx, ebx
0x18001b711  cmovz   eax, [rsp+118h+var_E8]
0x18001b716  mov     [r15], eax
0x18001b719  call    cs:__imp_RpcRevertToSelf
0x18001b71f  jmp     short loc_18001B726
0x18001b721  mov     ebx, 57h ; 'W'
0x18001b726  mov     eax, ebx
0x18001b728  mov     rcx, [rsp+118h+var_58]
0x18001b730  xor     rcx, rsp; StackCookie
0x18001b733  call    __security_check_cookie
0x18001b738  add     rsp, 0D8h
0x18001b73f  pop     r15
0x18001b741  pop     r14
0x18001b743  pop     r13
0x18001b745  pop     r12
0x18001b747  pop     rdi
0x18001b748  pop     rsi
0x18001b749  pop     rbp
0x18001b74a  pop     rbx
0x18001b74b  retn
```
