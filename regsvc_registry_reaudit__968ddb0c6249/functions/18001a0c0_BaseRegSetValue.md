# BaseRegSetValue

- ea: `0x18001a0c0`
- end: `0x18001a198`
- name: `BaseRegSetValue`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180007740`
- `0x180008042`
- `0x18001a0c0`
- `0x18001d1f0`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18001a131`
- `RPCRT4!RpcRaiseException` at `0x18001a13a`
- `RPCRT4!RpcRaiseException` at `0x18001a14f`
- `RPCRT4!RpcRaiseException` at `0x18001a131`
- `RPCRT4!RpcRaiseException` at `0x18001a13a`
- `RPCRT4!RpcRaiseException` at `0x18001a14f`
- `RPCRT4!RpcImpersonateClient` at `0x18001a143`
- `RPCRT4!RpcImpersonateClient` at `0x18001a143`
- `RPCRT4!RpcRevertToSelf` at `0x18001a174`
- `RPCRT4!RpcRevertToSelf` at `0x18001a174`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001a116`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001a116`

## pseudocode

```c
__int64 __fastcall BaseRegSetValue(_QWORD *a1, __int64 a2, unsigned int a3, __int64 a4, int a5)
{
  unsigned int v9; // ebx
  RPC_STATUS v10; // eax
  RPC_STATUS v11; // eax
  int RpcCallAttributes; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v14[36]; // [rsp+34h] [rbp-B4h] BYREF
  unsigned int v15; // [rsp+58h] [rbp-90h]

  if ( a1 )
  {
    memset_0(v14, 0, 0x74u);
    RpcCallAttributes = 3;
    v10 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
    if ( v10 != 1746 )
    {
      if ( v10 )
        RpcRaiseException(v10);
      if ( v15 < 6 )
        RpcRaiseException(5);
    }
    v11 = RpcImpersonateClient(0);
    if ( v11 )
      RpcRaiseException(v11);
    v9 = BaseRegSetValueInternal(*a1, a2, a3, a4, a5);
    RpcRevertToSelf();
  }
  else
  {
    return 87;
  }
  return v9;
}

```

## disassembly

```asm
0x18001a0c0  push    rbx
0x18001a0c2  push    rbp
0x18001a0c3  push    rsi
0x18001a0c4  push    rdi
0x18001a0c5  sub     rsp, 0C8h
0x18001a0cc  mov     rax, cs:__security_cookie
0x18001a0d3  xor     rax, rsp
0x18001a0d6  mov     [rsp+0E8h+var_38], rax
0x18001a0de  mov     rbp, r9
0x18001a0e1  mov     esi, r8d
0x18001a0e4  mov     rdi, rdx
0x18001a0e7  mov     rbx, rcx
0x18001a0ea  test    rcx, rcx
0x18001a0ed  jnz     short loc_18001A0F7
0x18001a0ef  lea     ebx, [rcx+57h]
0x18001a0f2  jmp     loc_18001A17A
0x18001a0f7  xor     edx, edx; Val
0x18001a0f9  lea     rcx, [rsp+0E8h+var_B4]; void *
0x18001a0fe  lea     r8d, [rdx+74h]; Size
0x18001a102  call    memset_0
0x18001a107  lea     rdx, [rsp+0E8h+RpcCallAttributes]; RpcCallAttributes
0x18001a10c  mov     [rsp+0E8h+RpcCallAttributes], 3
0x18001a114  xor     ecx, ecx; ClientBinding
0x18001a116  call    cs:__imp_RpcServerInqCallAttributesW
0x18001a11c  cmp     eax, 6D2h
0x18001a121  jz      short loc_18001A141
0x18001a123  test    eax, eax
0x18001a125  jnz     short loc_18001A138
0x18001a127  cmp     [rsp+0E8h+var_90], 6
0x18001a12c  jnb     short loc_18001A141
0x18001a12e  lea     ecx, [rax+5]; exception
0x18001a131  call    cs:__imp_RpcRaiseException
0x18001a137  int     3; Trap to Debugger
0x18001a138  mov     ecx, eax; exception
0x18001a13a  call    cs:__imp_RpcRaiseException
0x18001a140  int     3; Trap to Debugger
0x18001a141  xor     ecx, ecx; BindingHandle
0x18001a143  call    cs:__imp_RpcImpersonateClient
0x18001a149  test    eax, eax
0x18001a14b  jz      short loc_18001A156
0x18001a14d  mov     ecx, eax; exception
0x18001a14f  call    cs:__imp_RpcRaiseException
0x18001a155  int     3; Trap to Debugger
0x18001a156  mov     eax, [rsp+0E8h+arg_20]
0x18001a15d  mov     r9, rbp
0x18001a160  mov     rcx, [rbx]
0x18001a163  mov     r8d, esi
0x18001a166  mov     rdx, rdi
0x18001a169  mov     [rsp+0E8h+var_C8], eax
0x18001a16d  call    BaseRegSetValueInternal
0x18001a172  mov     ebx, eax
0x18001a174  call    cs:__imp_RpcRevertToSelf
0x18001a17a  mov     eax, ebx
0x18001a17c  mov     rcx, [rsp+0E8h+var_38]
0x18001a184  xor     rcx, rsp; StackCookie
0x18001a187  call    __security_check_cookie
0x18001a18c  add     rsp, 0C8h
0x18001a193  pop     rdi
0x18001a194  pop     rsi
0x18001a195  pop     rbp
0x18001a196  pop     rbx
0x18001a197  retn
```
