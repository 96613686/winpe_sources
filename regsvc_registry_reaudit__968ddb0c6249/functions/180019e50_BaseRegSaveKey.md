# BaseRegSaveKey

- ea: `0x180019e50`
- end: `0x180019f12`
- name: `BaseRegSaveKey`
- size: `194`
- prototype: `__int64 __fastcall(HANDLE *, __int16 *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180007740`
- `0x180008042`
- `0x180019e50`
- `0x18001d008`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180019eba`
- `RPCRT4!RpcRaiseException` at `0x180019ec3`
- `RPCRT4!RpcRaiseException` at `0x180019ed8`
- `RPCRT4!RpcRaiseException` at `0x180019eba`
- `RPCRT4!RpcRaiseException` at `0x180019ec3`
- `RPCRT4!RpcRaiseException` at `0x180019ed8`
- `RPCRT4!RpcImpersonateClient` at `0x180019ecc`
- `RPCRT4!RpcImpersonateClient` at `0x180019ecc`
- `RPCRT4!RpcRevertToSelf` at `0x180019eef`
- `RPCRT4!RpcRevertToSelf` at `0x180019eef`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180019e9f`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180019e9f`

## pseudocode

```c
__int64 __fastcall BaseRegSaveKey(HANDLE *a1, __int16 *a2, __int64 a3)
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
    v6 = BaseRegSaveKeyInternal(*a1, a2, a3);
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
0x180019e50  push    rbx
0x180019e52  push    rsi
0x180019e53  push    rdi
0x180019e54  sub     rsp, 0B0h
0x180019e5b  mov     rax, cs:__security_cookie
0x180019e62  xor     rax, rsp
0x180019e65  mov     [rsp+0C8h+var_28], rax
0x180019e6d  mov     rsi, r8
0x180019e70  mov     rdi, rdx
0x180019e73  mov     rbx, rcx
0x180019e76  test    rcx, rcx
0x180019e79  jnz     short loc_180019E80
0x180019e7b  lea     ebx, [rcx+57h]
0x180019e7e  jmp     short loc_180019EF5
0x180019e80  xor     edx, edx; Val
0x180019e82  lea     rcx, [rsp+0C8h+var_A4]; void *
0x180019e87  lea     r8d, [rdx+74h]; Size
0x180019e8b  call    memset_0
0x180019e90  lea     rdx, [rsp+0C8h+RpcCallAttributes]; RpcCallAttributes
0x180019e95  mov     [rsp+0C8h+RpcCallAttributes], 3
0x180019e9d  xor     ecx, ecx; ClientBinding
0x180019e9f  call    cs:__imp_RpcServerInqCallAttributesW
0x180019ea5  cmp     eax, 6D2h
0x180019eaa  jz      short loc_180019ECA
0x180019eac  test    eax, eax
0x180019eae  jnz     short loc_180019EC1
0x180019eb0  cmp     [rsp+0C8h+var_80], 6
0x180019eb5  jnb     short loc_180019ECA
0x180019eb7  lea     ecx, [rax+5]; exception
0x180019eba  call    cs:__imp_RpcRaiseException
0x180019ec0  int     3; Trap to Debugger
0x180019ec1  mov     ecx, eax; exception
0x180019ec3  call    cs:__imp_RpcRaiseException
0x180019ec9  int     3; Trap to Debugger
0x180019eca  xor     ecx, ecx; BindingHandle
0x180019ecc  call    cs:__imp_RpcImpersonateClient
0x180019ed2  test    eax, eax
0x180019ed4  jz      short loc_180019EDF
0x180019ed6  mov     ecx, eax; exception
0x180019ed8  call    cs:__imp_RpcRaiseException
0x180019ede  int     3; Trap to Debugger
0x180019edf  mov     rcx, [rbx]; KeyHandle
0x180019ee2  mov     r8, rsi
0x180019ee5  mov     rdx, rdi
0x180019ee8  call    BaseRegSaveKeyInternal
0x180019eed  mov     ebx, eax
0x180019eef  call    cs:__imp_RpcRevertToSelf
0x180019ef5  mov     eax, ebx
0x180019ef7  mov     rcx, [rsp+0C8h+var_28]
0x180019eff  xor     rcx, rsp; StackCookie
0x180019f02  call    __security_check_cookie
0x180019f07  add     rsp, 0B0h
0x180019f0e  pop     rdi
0x180019f0f  pop     rsi
0x180019f10  pop     rbx
0x180019f11  retn
```
