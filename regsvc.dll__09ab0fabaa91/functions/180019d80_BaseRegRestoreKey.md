# BaseRegRestoreKey

- ea: `0x180019d80`
- end: `0x180019e42`
- name: `BaseRegRestoreKey`
- size: `194`
- prototype: `__int64 __fastcall(HANDLE *, __int16 *, ULONG)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180007740`
- `0x180008042`
- `0x180019d80`
- `0x18001ccac`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180019dea`
- `RPCRT4!RpcRaiseException` at `0x180019df3`
- `RPCRT4!RpcRaiseException` at `0x180019e08`
- `RPCRT4!RpcRaiseException` at `0x180019dea`
- `RPCRT4!RpcRaiseException` at `0x180019df3`
- `RPCRT4!RpcRaiseException` at `0x180019e08`
- `RPCRT4!RpcImpersonateClient` at `0x180019dfc`
- `RPCRT4!RpcImpersonateClient` at `0x180019dfc`
- `RPCRT4!RpcRevertToSelf` at `0x180019e1f`
- `RPCRT4!RpcRevertToSelf` at `0x180019e1f`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180019dcf`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180019dcf`

## pseudocode

```c
__int64 __fastcall BaseRegRestoreKey(HANDLE *a1, __int16 *a2, ULONG a3)
{
  ULONG v6; // ebx
  RPC_STATUS v7; // eax
  RPC_STATUS v8; // eax
  int RpcCallAttributes; // [rsp+20h] [rbp-A8h] BYREF
  _BYTE v11[36]; // [rsp+24h] [rbp-A4h] BYREF
  unsigned int v12; // [rsp+48h] [rbp-80h]

  if ( a1 )
  {
    memset_0(v11, 0, 0x74u);
    RpcCallAttributes = 3;
    v7 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
    if ( v7 != 1746 )
    {
      if ( v7 )
        RpcRaiseException(v7);
      if ( v12 < 6 )
        RpcRaiseException(5);
    }
    v8 = RpcImpersonateClient(0);
    if ( v8 )
      RpcRaiseException(v8);
    v6 = BaseRegRestoreKeyInternal(*a1, a2, a3);
    RpcRevertToSelf();
  }
  else
  {
    return 87;
  }
  return v6;
}

```

## disassembly

```asm
0x180019d80  push    rbx
0x180019d82  push    rsi
0x180019d83  push    rdi
0x180019d84  sub     rsp, 0B0h
0x180019d8b  mov     rax, cs:__security_cookie
0x180019d92  xor     rax, rsp
0x180019d95  mov     [rsp+0C8h+var_28], rax
0x180019d9d  mov     esi, r8d
0x180019da0  mov     rdi, rdx
0x180019da3  mov     rbx, rcx
0x180019da6  test    rcx, rcx
0x180019da9  jnz     short loc_180019DB0
0x180019dab  lea     ebx, [rcx+57h]
0x180019dae  jmp     short loc_180019E25
0x180019db0  xor     edx, edx; Val
0x180019db2  lea     rcx, [rsp+0C8h+var_A4]; void *
0x180019db7  lea     r8d, [rdx+74h]; Size
0x180019dbb  call    memset_0
0x180019dc0  lea     rdx, [rsp+0C8h+RpcCallAttributes]; RpcCallAttributes
0x180019dc5  mov     [rsp+0C8h+RpcCallAttributes], 3
0x180019dcd  xor     ecx, ecx; ClientBinding
0x180019dcf  call    cs:__imp_RpcServerInqCallAttributesW
0x180019dd5  cmp     eax, 6D2h
0x180019dda  jz      short loc_180019DFA
0x180019ddc  test    eax, eax
0x180019dde  jnz     short loc_180019DF1
0x180019de0  cmp     [rsp+0C8h+var_80], 6
0x180019de5  jnb     short loc_180019DFA
0x180019de7  lea     ecx, [rax+5]; exception
0x180019dea  call    cs:__imp_RpcRaiseException
0x180019df0  int     3; Trap to Debugger
0x180019df1  mov     ecx, eax; exception
0x180019df3  call    cs:__imp_RpcRaiseException
0x180019df9  int     3; Trap to Debugger
0x180019dfa  xor     ecx, ecx; BindingHandle
0x180019dfc  call    cs:__imp_RpcImpersonateClient
0x180019e02  test    eax, eax
0x180019e04  jz      short loc_180019E0F
0x180019e06  mov     ecx, eax; exception
0x180019e08  call    cs:__imp_RpcRaiseException
0x180019e0e  int     3; Trap to Debugger
0x180019e0f  mov     rcx, [rbx]; KeyHandle
0x180019e12  mov     r8d, esi
0x180019e15  mov     rdx, rdi
0x180019e18  call    BaseRegRestoreKeyInternal
0x180019e1d  mov     ebx, eax
0x180019e1f  call    cs:__imp_RpcRevertToSelf
0x180019e25  mov     eax, ebx
0x180019e27  mov     rcx, [rsp+0C8h+var_28]
0x180019e2f  xor     rcx, rsp; StackCookie
0x180019e32  call    __security_check_cookie
0x180019e37  add     rsp, 0B0h
0x180019e3e  pop     rdi
0x180019e3f  pop     rsi
0x180019e40  pop     rbx
0x180019e41  retn
```
