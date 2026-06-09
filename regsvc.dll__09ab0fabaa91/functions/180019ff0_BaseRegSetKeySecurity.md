# BaseRegSetKeySecurity

- ea: `0x180019ff0`
- end: `0x18001a0b0`
- name: `BaseRegSetKeySecurity`
- size: `192`
- prototype: `__int64 __fastcall(HANDLE *, SECURITY_INFORMATION)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180007740`
- `0x180008042`
- `0x180019ff0`
- `0x18001cc1c`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18001a059`
- `RPCRT4!RpcRaiseException` at `0x18001a062`
- `RPCRT4!RpcRaiseException` at `0x18001a077`
- `RPCRT4!RpcRaiseException` at `0x18001a059`
- `RPCRT4!RpcRaiseException` at `0x18001a062`
- `RPCRT4!RpcRaiseException` at `0x18001a077`
- `RPCRT4!RpcImpersonateClient` at `0x18001a06b`
- `RPCRT4!RpcImpersonateClient` at `0x18001a06b`
- `RPCRT4!RpcRevertToSelf` at `0x18001a08d`
- `RPCRT4!RpcRevertToSelf` at `0x18001a08d`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001a03e`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001a03e`

## pseudocode

```c
__int64 __fastcall BaseRegSetKeySecurity(HANDLE *a1, SECURITY_INFORMATION a2)
{
  unsigned int v4; // ebx
  RPC_STATUS v5; // eax
  RPC_STATUS v6; // eax
  int RpcCallAttributes; // [rsp+20h] [rbp-A8h] BYREF
  _BYTE v9[36]; // [rsp+24h] [rbp-A4h] BYREF
  unsigned int v10; // [rsp+48h] [rbp-80h]

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
    v4 = BaseRegSetKeySecurityInternal(*a1, a2);
  }
  else
  {
    v4 = 87;
  }
  RpcRevertToSelf();
  return v4;
}

```

## disassembly

```asm
0x180019ff0  push    rbx
0x180019ff2  push    rsi
0x180019ff3  push    rdi
0x180019ff4  sub     rsp, 0B0h
0x180019ffb  mov     rax, cs:__security_cookie
0x18001a002  xor     rax, rsp
0x18001a005  mov     [rsp+0C8h+var_28], rax
0x18001a00d  mov     rsi, r8
0x18001a010  mov     edi, edx
0x18001a012  mov     rbx, rcx
0x18001a015  test    rcx, rcx
0x18001a018  jnz     short loc_18001A01F
0x18001a01a  lea     ebx, [rcx+57h]
0x18001a01d  jmp     short loc_18001A08D
0x18001a01f  xor     edx, edx; Val
0x18001a021  lea     rcx, [rsp+0C8h+var_A4]; void *
0x18001a026  lea     r8d, [rdx+74h]; Size
0x18001a02a  call    memset_0
0x18001a02f  lea     rdx, [rsp+0C8h+RpcCallAttributes]; RpcCallAttributes
0x18001a034  mov     [rsp+0C8h+RpcCallAttributes], 3
0x18001a03c  xor     ecx, ecx; ClientBinding
0x18001a03e  call    cs:__imp_RpcServerInqCallAttributesW
0x18001a044  cmp     eax, 6D2h
0x18001a049  jz      short loc_18001A069
0x18001a04b  test    eax, eax
0x18001a04d  jnz     short loc_18001A060
0x18001a04f  cmp     [rsp+0C8h+var_80], 6
0x18001a054  jnb     short loc_18001A069
0x18001a056  lea     ecx, [rax+5]; exception
0x18001a059  call    cs:__imp_RpcRaiseException
0x18001a05f  int     3; Trap to Debugger
0x18001a060  mov     ecx, eax; exception
0x18001a062  call    cs:__imp_RpcRaiseException
0x18001a068  int     3; Trap to Debugger
0x18001a069  xor     ecx, ecx; BindingHandle
0x18001a06b  call    cs:__imp_RpcImpersonateClient
0x18001a071  test    eax, eax
0x18001a073  jz      short loc_18001A07E
0x18001a075  mov     ecx, eax; exception
0x18001a077  call    cs:__imp_RpcRaiseException
0x18001a07d  int     3; Trap to Debugger
0x18001a07e  mov     rcx, [rbx]; Handle
0x18001a081  mov     r8, rsi
0x18001a084  mov     edx, edi; SecurityInformation
0x18001a086  call    BaseRegSetKeySecurityInternal
0x18001a08b  mov     ebx, eax
0x18001a08d  call    cs:__imp_RpcRevertToSelf
0x18001a093  mov     eax, ebx
0x18001a095  mov     rcx, [rsp+0C8h+var_28]
0x18001a09d  xor     rcx, rsp; StackCookie
0x18001a0a0  call    __security_check_cookie
0x18001a0a5  add     rsp, 0B0h
0x18001a0ac  pop     rdi
0x18001a0ad  pop     rsi
0x18001a0ae  pop     rbx
0x18001a0af  retn
```
