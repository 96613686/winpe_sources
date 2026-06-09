# PerflibV2QueryCounterData

- ea: `0x180018c80`
- end: `0x180018dc0`
- name: `PerflibV2QueryCounterData`
- size: `320`
- prototype: `__int64 __usercall@<rax>(struct _PERF_QUERY *@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180001520`
- `0x180007740`
- `0x180008042`
- `0x180016574`
- `0x180018c80`
- `0x180019178`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180018d3a`
- `RPCRT4!RpcRaiseException` at `0x180018d43`
- `RPCRT4!RpcRaiseException` at `0x180018d58`
- `RPCRT4!RpcRaiseException` at `0x180018d3a`
- `RPCRT4!RpcRaiseException` at `0x180018d43`
- `RPCRT4!RpcRaiseException` at `0x180018d58`
- `RPCRT4!RpcImpersonateClient` at `0x180018d4c`
- `RPCRT4!RpcImpersonateClient` at `0x180018d4c`
- `RPCRT4!RpcRevertToSelf` at `0x180018d7c`
- `RPCRT4!RpcRevertToSelf` at `0x180018d7c`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180018d1f`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180018d1f`

## pseudocode

```c
__int64 __fastcall PerflibV2QueryCounterData(
        struct _PERF_QUERY *a1,
        unsigned int a2,
        unsigned int *a3,
        unsigned int *a4,
        _BYTE *a5)
{
  unsigned int IsLocalQueryFromHandle; // eax
  unsigned int CounterData; // ebx
  RPC_STATUS v11; // eax
  RPC_STATUS v12; // eax
  int RpcCallAttributes; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v15[36]; // [rsp+24h] [rbp-C4h] BYREF
  unsigned int v16; // [rsp+48h] [rbp-A0h]

  if ( a4 )
    *a4 = 0;
  if ( !a3 )
    return 87;
  *a3 = 0;
  if ( a2 )
  {
    if ( !a5 )
      return 87;
    a5[a2 - 1] = 0;
    *a5 = 0;
  }
  if ( !a1 )
    return 87;
  IsLocalQueryFromHandle = PerflibciIsLocalQueryFromHandle(a1);
  CounterData = IsLocalQueryFromHandle;
  if ( IsLocalQueryFromHandle )
  {
    if ( IsLocalQueryFromHandle != 13 )
      return CounterData;
    PerflibciReleaseMutex(*(_QWORD *)a1);
    return 87;
  }
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
  CounterData = PerflibciLocalQueryCounterData(a1, a5, a2, a4);
  if ( !CounterData )
    *a3 = *a4;
  RpcRevertToSelf();
  PerflibciReleaseMutex(*(_QWORD *)a1);
  return CounterData;
}

```

## disassembly

```asm
0x180018c80  push    rbx
0x180018c82  push    rbp
0x180018c83  push    rsi
0x180018c84  push    rdi
0x180018c85  push    r14
0x180018c87  push    r15
0x180018c89  sub     rsp, 0B8h
0x180018c90  mov     rax, cs:__security_cookie
0x180018c97  xor     rax, rsp
0x180018c9a  mov     [rsp+0E8h+var_48], rax
0x180018ca2  mov     rsi, [rsp+0E8h+arg_20]
0x180018caa  mov     r15, r9
0x180018cad  mov     r14, r8
0x180018cb0  mov     ebp, edx
0x180018cb2  mov     rdi, rcx
0x180018cb5  test    r9, r9
0x180018cb8  jz      short loc_180018CC1
0x180018cba  mov     dword ptr [r9], 0
0x180018cc1  test    r14, r14
0x180018cc4  jz      loc_180018D99
0x180018cca  mov     dword ptr [r8], 0
0x180018cd1  test    ebp, ebp
0x180018cd3  jz      short loc_180018CE8
0x180018cd5  test    rsi, rsi
0x180018cd8  jz      loc_180018D99
0x180018cde  lea     eax, [rdx-1]
0x180018ce1  mov     byte ptr [rax+rsi], 0
0x180018ce5  mov     byte ptr [rsi], 0
0x180018ce8  test    rdi, rdi
0x180018ceb  jz      loc_180018D99
0x180018cf1  call    PerflibciIsLocalQueryFromHandle
0x180018cf6  mov     ebx, eax
0x180018cf8  test    eax, eax
0x180018cfa  jnz     loc_180018D8C
0x180018d00  xor     edx, edx; Val
0x180018d02  lea     r8d, [rax+74h]; Size
0x180018d06  lea     rcx, [rsp+0E8h+var_C4]; void *
0x180018d0b  call    memset_0
0x180018d10  lea     rdx, [rsp+0E8h+RpcCallAttributes]; RpcCallAttributes
0x180018d15  mov     [rsp+0E8h+RpcCallAttributes], 3
0x180018d1d  xor     ecx, ecx; ClientBinding
0x180018d1f  call    cs:__imp_RpcServerInqCallAttributesW
0x180018d25  cmp     eax, 6D2h
0x180018d2a  jz      short loc_180018D4A
0x180018d2c  test    eax, eax
0x180018d2e  jnz     short loc_180018D41
0x180018d30  cmp     [rsp+0E8h+var_A0], 6
0x180018d35  jnb     short loc_180018D4A
0x180018d37  lea     ecx, [rbx+5]; exception
0x180018d3a  call    cs:__imp_RpcRaiseException
0x180018d40  int     3; Trap to Debugger
0x180018d41  mov     ecx, eax; exception
0x180018d43  call    cs:__imp_RpcRaiseException
0x180018d49  int     3; Trap to Debugger
0x180018d4a  xor     ecx, ecx; BindingHandle
0x180018d4c  call    cs:__imp_RpcImpersonateClient
0x180018d52  test    eax, eax
0x180018d54  jz      short loc_180018D5F
0x180018d56  mov     ecx, eax; exception
0x180018d58  call    cs:__imp_RpcRaiseException
0x180018d5e  int     3; Trap to Debugger
0x180018d5f  mov     r9, r15
0x180018d62  mov     r8d, ebp
0x180018d65  mov     rdx, rsi
0x180018d68  mov     rcx, rdi; struct _PERF_QUERY *
0x180018d6b  call    PerflibciLocalQueryCounterData
0x180018d70  mov     ebx, eax
0x180018d72  test    eax, eax
0x180018d74  jnz     short loc_180018D7C
0x180018d76  mov     eax, [r15]
0x180018d79  mov     [r14], eax
0x180018d7c  call    cs:__imp_RpcRevertToSelf
0x180018d82  mov     rcx, [rdi]
0x180018d85  call    PerflibciReleaseMutex
0x180018d8a  jmp     short loc_180018D9E
0x180018d8c  cmp     eax, 0Dh
0x180018d8f  jnz     short loc_180018D9E
0x180018d91  mov     rcx, [rdi]
0x180018d94  call    PerflibciReleaseMutex
0x180018d99  mov     ebx, 57h ; 'W'
0x180018d9e  mov     eax, ebx
0x180018da0  mov     rcx, [rsp+0E8h+var_48]
0x180018da8  xor     rcx, rsp; StackCookie
0x180018dab  call    __security_check_cookie
0x180018db0  add     rsp, 0B8h
0x180018db7  pop     r15
0x180018db9  pop     r14
0x180018dbb  pop     rdi
0x180018dbc  pop     rsi
0x180018dbd  pop     rbp
0x180018dbe  pop     rbx
0x180018dbf  retn
```
