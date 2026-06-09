# PerflibV2QueryCounterInfo

- ea: `0x180018dd0`
- end: `0x180018f10`
- name: `PerflibV2QueryCounterInfo`
- size: `320`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int, _DWORD *, _DWORD *, _BYTE *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180007740`
- `0x180008042`
- `0x180016574`
- `0x1800165d0`
- `0x180018dd0`
- `0x180019178`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180018e8a`
- `RPCRT4!RpcRaiseException` at `0x180018e93`
- `RPCRT4!RpcRaiseException` at `0x180018ea8`
- `RPCRT4!RpcRaiseException` at `0x180018e8a`
- `RPCRT4!RpcRaiseException` at `0x180018e93`
- `RPCRT4!RpcRaiseException` at `0x180018ea8`
- `RPCRT4!RpcImpersonateClient` at `0x180018e9c`
- `RPCRT4!RpcImpersonateClient` at `0x180018e9c`
- `RPCRT4!RpcRevertToSelf` at `0x180018ecc`
- `RPCRT4!RpcRevertToSelf` at `0x180018ecc`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180018e6f`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180018e6f`

## pseudocode

```c
__int64 __fastcall PerflibV2QueryCounterInfo(_QWORD *a1, unsigned int a2, _DWORD *a3, _DWORD *a4, _BYTE *a5)
{
  unsigned int IsLocalQueryFromHandle; // eax
  unsigned int CounterInfo; // ebx
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
  CounterInfo = IsLocalQueryFromHandle;
  if ( IsLocalQueryFromHandle )
  {
    if ( IsLocalQueryFromHandle != 13 )
      return CounterInfo;
    PerflibciReleaseMutex(*a1);
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
      RpcRaiseException(CounterInfo + 5);
  }
  v12 = RpcImpersonateClient(0);
  if ( v12 )
    RpcRaiseException(v12);
  CounterInfo = PerflibciLocalQueryCounterInfo(a1, a5, a2, a4);
  if ( !CounterInfo )
    *a3 = *a4;
  RpcRevertToSelf();
  PerflibciReleaseMutex(*a1);
  return CounterInfo;
}

```

## disassembly

```asm
0x180018dd0  push    rbx
0x180018dd2  push    rbp
0x180018dd3  push    rsi
0x180018dd4  push    rdi
0x180018dd5  push    r14
0x180018dd7  push    r15
0x180018dd9  sub     rsp, 0B8h
0x180018de0  mov     rax, cs:__security_cookie
0x180018de7  xor     rax, rsp
0x180018dea  mov     [rsp+0E8h+var_48], rax
0x180018df2  mov     rsi, [rsp+0E8h+arg_20]
0x180018dfa  mov     r15, r9
0x180018dfd  mov     r14, r8
0x180018e00  mov     ebp, edx
0x180018e02  mov     rdi, rcx
0x180018e05  test    r9, r9
0x180018e08  jz      short loc_180018E11
0x180018e0a  mov     dword ptr [r9], 0
0x180018e11  test    r14, r14
0x180018e14  jz      loc_180018EE9
0x180018e1a  mov     dword ptr [r8], 0
0x180018e21  test    ebp, ebp
0x180018e23  jz      short loc_180018E38
0x180018e25  test    rsi, rsi
0x180018e28  jz      loc_180018EE9
0x180018e2e  lea     eax, [rdx-1]
0x180018e31  mov     byte ptr [rax+rsi], 0
0x180018e35  mov     byte ptr [rsi], 0
0x180018e38  test    rdi, rdi
0x180018e3b  jz      loc_180018EE9
0x180018e41  call    PerflibciIsLocalQueryFromHandle
0x180018e46  mov     ebx, eax
0x180018e48  test    eax, eax
0x180018e4a  jnz     loc_180018EDC
0x180018e50  xor     edx, edx; Val
0x180018e52  lea     r8d, [rax+74h]; Size
0x180018e56  lea     rcx, [rsp+0E8h+var_C4]; void *
0x180018e5b  call    memset_0
0x180018e60  lea     rdx, [rsp+0E8h+RpcCallAttributes]; RpcCallAttributes
0x180018e65  mov     [rsp+0E8h+RpcCallAttributes], 3
0x180018e6d  xor     ecx, ecx; ClientBinding
0x180018e6f  call    cs:__imp_RpcServerInqCallAttributesW
0x180018e75  cmp     eax, 6D2h
0x180018e7a  jz      short loc_180018E9A
0x180018e7c  test    eax, eax
0x180018e7e  jnz     short loc_180018E91
0x180018e80  cmp     [rsp+0E8h+var_A0], 6
0x180018e85  jnb     short loc_180018E9A
0x180018e87  lea     ecx, [rbx+5]; exception
0x180018e8a  call    cs:__imp_RpcRaiseException
0x180018e90  int     3; Trap to Debugger
0x180018e91  mov     ecx, eax; exception
0x180018e93  call    cs:__imp_RpcRaiseException
0x180018e99  int     3; Trap to Debugger
0x180018e9a  xor     ecx, ecx; BindingHandle
0x180018e9c  call    cs:__imp_RpcImpersonateClient
0x180018ea2  test    eax, eax
0x180018ea4  jz      short loc_180018EAF
0x180018ea6  mov     ecx, eax; exception
0x180018ea8  call    cs:__imp_RpcRaiseException
0x180018eae  int     3; Trap to Debugger
0x180018eaf  mov     r9, r15
0x180018eb2  mov     r8d, ebp
0x180018eb5  mov     rdx, rsi
0x180018eb8  mov     rcx, rdi
0x180018ebb  call    PerflibciLocalQueryCounterInfo
0x180018ec0  mov     ebx, eax
0x180018ec2  test    eax, eax
0x180018ec4  jnz     short loc_180018ECC
0x180018ec6  mov     eax, [r15]
0x180018ec9  mov     [r14], eax
0x180018ecc  call    cs:__imp_RpcRevertToSelf
0x180018ed2  mov     rcx, [rdi]
0x180018ed5  call    PerflibciReleaseMutex
0x180018eda  jmp     short loc_180018EEE
0x180018edc  cmp     eax, 0Dh
0x180018edf  jnz     short loc_180018EEE
0x180018ee1  mov     rcx, [rdi]
0x180018ee4  call    PerflibciReleaseMutex
0x180018ee9  mov     ebx, 57h ; 'W'
0x180018eee  mov     eax, ebx
0x180018ef0  mov     rcx, [rsp+0E8h+var_48]
0x180018ef8  xor     rcx, rsp; StackCookie
0x180018efb  call    __security_check_cookie
0x180018f00  add     rsp, 0B8h
0x180018f07  pop     r15
0x180018f09  pop     r14
0x180018f0b  pop     rdi
0x180018f0c  pop     rsi
0x180018f0d  pop     rbp
0x180018f0e  pop     rbx
0x180018f0f  retn
```
