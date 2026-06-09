# BaseRegFlushKey

- ea: `0x1800197b0`
- end: `0x18001988d`
- name: `BaseRegFlushKey`
- size: `221`
- prototype: `__int64 __fastcall(HANDLE *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180007740`
- `0x180008042`
- `0x1800197b0`

## import_xrefs

- `ntdll!NtFlushKey` at `0x180019858`
- `ntdll!NtFlushKey` at `0x180019858`
- `ntdll!RtlNtStatusToDosError` at `0x180019860`
- `ntdll!RtlNtStatusToDosError` at `0x180019860`
- `RPCRT4!RpcRaiseException` at `0x180019815`
- `RPCRT4!RpcRaiseException` at `0x18001981e`
- `RPCRT4!RpcRaiseException` at `0x180019833`
- `RPCRT4!RpcRaiseException` at `0x180019815`
- `RPCRT4!RpcRaiseException` at `0x18001981e`
- `RPCRT4!RpcRaiseException` at `0x180019833`
- `RPCRT4!RpcImpersonateClient` at `0x180019827`
- `RPCRT4!RpcImpersonateClient` at `0x180019827`
- `RPCRT4!RpcRevertToSelf` at `0x18001986c`
- `RPCRT4!RpcRevertToSelf` at `0x18001986c`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800197fa`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800197fa`

## pseudocode

```c
__int64 __fastcall BaseRegFlushKey(HANDLE *a1)
{
  ULONG v2; // ebx
  RPC_STATUS v3; // eax
  RPC_STATUS v4; // eax
  NTSTATUS v5; // eax
  int RpcCallAttributes; // [rsp+20h] [rbp-98h] BYREF
  _BYTE v8[36]; // [rsp+24h] [rbp-94h] BYREF
  unsigned int v9; // [rsp+48h] [rbp-70h]

  if ( a1 )
  {
    memset_0(v8, 0, 0x74u);
    RpcCallAttributes = 3;
    v3 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
    if ( v3 != 1746 )
    {
      if ( v3 )
        RpcRaiseException(v3);
      if ( v9 < 6 )
        RpcRaiseException(5);
    }
    v4 = RpcImpersonateClient(0);
    if ( v4 )
      RpcRaiseException(v4);
    if ( *a1 == (HANDLE)-2147483644LL || *a1 == (HANDLE)-2147483568LL || *a1 == (HANDLE)-2147483552LL )
    {
      v2 = 0;
    }
    else
    {
      v5 = NtFlushKey(*a1);
      v2 = RtlNtStatusToDosError(v5);
    }
    RpcRevertToSelf();
  }
  else
  {
    return 87;
  }
  return v2;
}

```

## disassembly

```asm
0x1800197b0  push    rbx
0x1800197b2  sub     rsp, 0B0h
0x1800197b9  mov     rax, cs:__security_cookie
0x1800197c0  xor     rax, rsp
0x1800197c3  mov     [rsp+0B8h+var_18], rax
0x1800197cb  mov     rbx, rcx
0x1800197ce  test    rcx, rcx
0x1800197d1  jnz     short loc_1800197DB
0x1800197d3  lea     ebx, [rcx+57h]
0x1800197d6  jmp     loc_180019872
0x1800197db  xor     edx, edx; Val
0x1800197dd  lea     rcx, [rsp+0B8h+var_94]; void *
0x1800197e2  lea     r8d, [rdx+74h]; Size
0x1800197e6  call    memset_0
0x1800197eb  lea     rdx, [rsp+0B8h+RpcCallAttributes]; RpcCallAttributes
0x1800197f0  mov     [rsp+0B8h+RpcCallAttributes], 3
0x1800197f8  xor     ecx, ecx; ClientBinding
0x1800197fa  call    cs:__imp_RpcServerInqCallAttributesW
0x180019800  cmp     eax, 6D2h
0x180019805  jz      short loc_180019825
0x180019807  test    eax, eax
0x180019809  jnz     short loc_18001981C
0x18001980b  cmp     [rsp+0B8h+var_70], 6
0x180019810  jnb     short loc_180019825
0x180019812  lea     ecx, [rax+5]; exception
0x180019815  call    cs:__imp_RpcRaiseException
0x18001981b  int     3; Trap to Debugger
0x18001981c  mov     ecx, eax; exception
0x18001981e  call    cs:__imp_RpcRaiseException
0x180019824  int     3; Trap to Debugger
0x180019825  xor     ecx, ecx; BindingHandle
0x180019827  call    cs:__imp_RpcImpersonateClient
0x18001982d  test    eax, eax
0x18001982f  jz      short loc_18001983A
0x180019831  mov     ecx, eax; exception
0x180019833  call    cs:__imp_RpcRaiseException
0x180019839  int     3; Trap to Debugger
0x18001983a  cmp     qword ptr [rbx], 0FFFFFFFF80000004h
0x180019841  jz      short loc_18001986A
0x180019843  cmp     qword ptr [rbx], 0FFFFFFFF80000050h
0x18001984a  jz      short loc_18001986A
0x18001984c  cmp     qword ptr [rbx], 0FFFFFFFF80000060h
0x180019853  jz      short loc_18001986A
0x180019855  mov     rcx, [rbx]; KeyHandle
0x180019858  call    cs:__imp_NtFlushKey
0x18001985e  mov     ecx, eax; Status
0x180019860  call    cs:__imp_RtlNtStatusToDosError
0x180019866  mov     ebx, eax
0x180019868  jmp     short loc_18001986C
0x18001986a  xor     ebx, ebx
0x18001986c  call    cs:__imp_RpcRevertToSelf
0x180019872  mov     eax, ebx
0x180019874  mov     rcx, [rsp+0B8h+var_18]
0x18001987c  xor     rcx, rsp; StackCookie
0x18001987f  call    __security_check_cookie
0x180019884  add     rsp, 0B0h
0x18001988b  pop     rbx
0x18001988c  retn
```
