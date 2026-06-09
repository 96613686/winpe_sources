# PerflibV2QueryCounterSetRegistrationInfo

- ea: `0x180018f20`
- end: `0x180019055`
- name: `PerflibV2QueryCounterSetRegistrationInfo`
- size: `309`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x1800044a0`
- `0x180007740`
- `0x180008042`
- `0x180018f20`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180018fcd`
- `RPCRT4!RpcRaiseException` at `0x180018fdd`
- `RPCRT4!RpcRaiseException` at `0x180018ff2`
- `RPCRT4!RpcRaiseException` at `0x180018fcd`
- `RPCRT4!RpcRaiseException` at `0x180018fdd`
- `RPCRT4!RpcRaiseException` at `0x180018ff2`
- `RPCRT4!RpcImpersonateClient` at `0x180018fe6`
- `RPCRT4!RpcImpersonateClient` at `0x180018fe6`
- `RPCRT4!RpcRevertToSelf` at `0x180019026`
- `RPCRT4!RpcRevertToSelf` at `0x180019026`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180018fb2`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180018fb2`

## pseudocode

```c
__int64 __fastcall PerflibV2QueryCounterSetRegistrationInfo(
        __int64 a1,
        __int64 a2,
        const struct _GUID *a3,
        enum _PerfRegInfoType a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned __int8 *a9)
{
  RPC_STATUS v11; // eax
  unsigned int CounterSetRegInfo; // ebx
  RPC_STATUS v13; // eax
  int RpcCallAttributes; // [rsp+40h] [rbp-B8h] BYREF
  _BYTE v16[36]; // [rsp+44h] [rbp-B4h] BYREF
  unsigned int v17; // [rsp+68h] [rbp-90h]

  if ( a8 )
    *a8 = 0;
  if ( !a7 )
    return 87;
  *a7 = 0;
  if ( a6 )
  {
    if ( a9 )
    {
      a9[a6 - 1] = 0;
      *a9 = 0;
      goto LABEL_7;
    }
    return 87;
  }
LABEL_7:
  memset_0(v16, 0, 0x74u);
  RpcCallAttributes = 3;
  v11 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
  if ( v11 != 1746 )
  {
    if ( v11 )
      RpcRaiseException(v11);
    if ( v17 < 6 )
      RpcRaiseException(5);
  }
  v13 = RpcImpersonateClient(0);
  if ( v13 )
    RpcRaiseException(v13);
  CounterSetRegInfo = PerflibciLocalQueryCounterSetRegInfoEx(1u, a3, a4, a5, a9, a6, a8);
  if ( !CounterSetRegInfo )
    *a7 = *a8;
  RpcRevertToSelf();
  return CounterSetRegInfo;
}

```

## disassembly

```asm
0x180018f20  mov     [rsp+arg_0], rbx
0x180018f25  push    rbp
0x180018f26  push    rsi
0x180018f27  push    rdi
0x180018f28  push    r14
0x180018f2a  push    r15
0x180018f2c  sub     rsp, 0D0h
0x180018f33  mov     rax, cs:__security_cookie
0x180018f3a  xor     rax, rsp
0x180018f3d  mov     [rsp+0F8h+var_38], rax
0x180018f45  mov     rsi, [rsp+0F8h+arg_38]
0x180018f4d  mov     r15d, r9d
0x180018f50  mov     ebp, [rsp+0F8h+arg_28]
0x180018f57  mov     r14, r8
0x180018f5a  mov     rdi, [rsp+0F8h+arg_30]
0x180018f62  mov     rbx, [rsp+0F8h+arg_40]
0x180018f6a  test    rsi, rsi
0x180018f6d  jz      short loc_180018F75
0x180018f6f  mov     dword ptr [rsi], 0
0x180018f75  test    rdi, rdi
0x180018f78  jz      short loc_180018FD4
0x180018f7a  mov     dword ptr [rdi], 0
0x180018f80  test    ebp, ebp
0x180018f82  jz      short loc_180018F93
0x180018f84  test    rbx, rbx
0x180018f87  jz      short loc_180018FD4
0x180018f89  lea     eax, [rbp-1]
0x180018f8c  mov     byte ptr [rax+rbx], 0
0x180018f90  mov     byte ptr [rbx], 0
0x180018f93  xor     edx, edx; Val
0x180018f95  lea     rcx, [rsp+0F8h+var_B4]; void *
0x180018f9a  lea     r8d, [rdx+74h]; Size
0x180018f9e  call    memset_0
0x180018fa3  lea     rdx, [rsp+0F8h+RpcCallAttributes]; RpcCallAttributes
0x180018fa8  mov     [rsp+0F8h+RpcCallAttributes], 3
0x180018fb0  xor     ecx, ecx; ClientBinding
0x180018fb2  call    cs:__imp_RpcServerInqCallAttributesW
0x180018fb8  cmp     eax, 6D2h
0x180018fbd  jz      short loc_180018FE4
0x180018fbf  test    eax, eax
0x180018fc1  jnz     short loc_180018FDB
0x180018fc3  cmp     [rsp+0F8h+var_90], 6
0x180018fc8  jnb     short loc_180018FE4
0x180018fca  lea     ecx, [rax+5]; exception
0x180018fcd  call    cs:__imp_RpcRaiseException
0x180018fd3  int     3; Trap to Debugger
0x180018fd4  mov     ebx, 57h ; 'W'
0x180018fd9  jmp     short loc_18001902C
0x180018fdb  mov     ecx, eax; exception
0x180018fdd  call    cs:__imp_RpcRaiseException
0x180018fe3  int     3; Trap to Debugger
0x180018fe4  xor     ecx, ecx; BindingHandle
0x180018fe6  call    cs:__imp_RpcImpersonateClient
0x180018fec  test    eax, eax
0x180018fee  jz      short loc_180018FF9
0x180018ff0  mov     ecx, eax; exception
0x180018ff2  call    cs:__imp_RpcRaiseException
0x180018ff8  int     3; Trap to Debugger
0x180018ff9  mov     r9d, [rsp+0F8h+arg_20]; unsigned int
0x180019001  mov     r8d, r15d; enum _PerfRegInfoType
0x180019004  mov     [rsp+0F8h+var_C8], rsi; unsigned int *
0x180019009  mov     rdx, r14; struct _GUID *
0x18001900c  mov     [rsp+0F8h+var_D0], ebp; unsigned int
0x180019010  mov     cl, 1; unsigned __int8
0x180019012  mov     [rsp+0F8h+var_D8], rbx; unsigned __int8 *
0x180019017  call    ?PerflibciLocalQueryCounterSetRegInfoEx@@YAKEPEBU_GUID@@W4_PerfRegInfoType@@KPEAEKPEAK@Z; PerflibciLocalQueryCounterSetRegInfoEx(uchar,_GUID const *,_PerfRegInfoType,ulong,uchar *,ulong,ulong *)
0x18001901c  mov     ebx, eax
0x18001901e  test    eax, eax
0x180019020  jnz     short loc_180019026
0x180019022  mov     ecx, [rsi]
0x180019024  mov     [rdi], ecx
0x180019026  call    cs:__imp_RpcRevertToSelf
0x18001902c  mov     eax, ebx
0x18001902e  mov     rcx, [rsp+0F8h+var_38]
0x180019036  xor     rcx, rsp; StackCookie
0x180019039  call    __security_check_cookie
0x18001903e  mov     rbx, [rsp+0F8h+arg_0]
0x180019046  add     rsp, 0D0h
0x18001904d  pop     r15
0x18001904f  pop     r14
0x180019051  pop     rdi
0x180019052  pop     rsi
0x180019053  pop     rbp
0x180019054  retn
```
