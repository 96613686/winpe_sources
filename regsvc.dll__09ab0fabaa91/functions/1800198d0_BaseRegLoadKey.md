# BaseRegLoadKey

- ea: `0x1800198d0`
- end: `0x180019992`
- name: `BaseRegLoadKey`
- size: `194`
- prototype: `__int64 __fastcall(void **, struct _UNICODE_STRING *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180007740`
- `0x180008042`
- `0x1800198d0`
- `0x18001c180`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18001993a`
- `RPCRT4!RpcRaiseException` at `0x180019943`
- `RPCRT4!RpcRaiseException` at `0x180019958`
- `RPCRT4!RpcRaiseException` at `0x18001993a`
- `RPCRT4!RpcRaiseException` at `0x180019943`
- `RPCRT4!RpcRaiseException` at `0x180019958`
- `RPCRT4!RpcImpersonateClient` at `0x18001994c`
- `RPCRT4!RpcImpersonateClient` at `0x18001994c`
- `RPCRT4!RpcRevertToSelf` at `0x18001996f`
- `RPCRT4!RpcRevertToSelf` at `0x18001996f`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001991f`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001991f`

## pseudocode

```c
__int64 __fastcall BaseRegLoadKey(void **a1, struct _UNICODE_STRING *a2, unsigned __int16 *a3)
{
  ULONG KeyInternal; // ebx
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
    KeyInternal = BaseRegLoadKeyInternal(*a1, a2, a3);
    RpcRevertToSelf();
  }
  else
  {
    return 87;
  }
  return KeyInternal;
}

```

## disassembly

```asm
0x1800198d0  push    rbx
0x1800198d2  push    rsi
0x1800198d3  push    rdi
0x1800198d4  sub     rsp, 0B0h
0x1800198db  mov     rax, cs:__security_cookie
0x1800198e2  xor     rax, rsp
0x1800198e5  mov     [rsp+0C8h+var_28], rax
0x1800198ed  mov     rsi, r8
0x1800198f0  mov     rdi, rdx
0x1800198f3  mov     rbx, rcx
0x1800198f6  test    rcx, rcx
0x1800198f9  jnz     short loc_180019900
0x1800198fb  lea     ebx, [rcx+57h]
0x1800198fe  jmp     short loc_180019975
0x180019900  xor     edx, edx; Val
0x180019902  lea     rcx, [rsp+0C8h+var_A4]; void *
0x180019907  lea     r8d, [rdx+74h]; Size
0x18001990b  call    memset_0
0x180019910  lea     rdx, [rsp+0C8h+RpcCallAttributes]; RpcCallAttributes
0x180019915  mov     [rsp+0C8h+RpcCallAttributes], 3
0x18001991d  xor     ecx, ecx; ClientBinding
0x18001991f  call    cs:__imp_RpcServerInqCallAttributesW
0x180019925  cmp     eax, 6D2h
0x18001992a  jz      short loc_18001994A
0x18001992c  test    eax, eax
0x18001992e  jnz     short loc_180019941
0x180019930  cmp     [rsp+0C8h+var_80], 6
0x180019935  jnb     short loc_18001994A
0x180019937  lea     ecx, [rax+5]; exception
0x18001993a  call    cs:__imp_RpcRaiseException
0x180019940  int     3; Trap to Debugger
0x180019941  mov     ecx, eax; exception
0x180019943  call    cs:__imp_RpcRaiseException
0x180019949  int     3; Trap to Debugger
0x18001994a  xor     ecx, ecx; BindingHandle
0x18001994c  call    cs:__imp_RpcImpersonateClient
0x180019952  test    eax, eax
0x180019954  jz      short loc_18001995F
0x180019956  mov     ecx, eax; exception
0x180019958  call    cs:__imp_RpcRaiseException
0x18001995e  int     3; Trap to Debugger
0x18001995f  mov     rcx, [rbx]
0x180019962  mov     r8, rsi
0x180019965  mov     rdx, rdi
0x180019968  call    BaseRegLoadKeyInternal
0x18001996d  mov     ebx, eax
0x18001996f  call    cs:__imp_RpcRevertToSelf
0x180019975  mov     eax, ebx
0x180019977  mov     rcx, [rsp+0C8h+var_28]
0x18001997f  xor     rcx, rsp; StackCookie
0x180019982  call    __security_check_cookie
0x180019987  add     rsp, 0B0h
0x18001998e  pop     rdi
0x18001998f  pop     rsi
0x180019990  pop     rbx
0x180019991  retn
```
