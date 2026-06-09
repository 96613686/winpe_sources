# s_SrvRpcCryptFreeKey

- ea: `0x180003020`
- end: `0x180003118`
- name: `s_SrvRpcCryptFreeKey`
- size: `248`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003020`
- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180003038`
- `RPCRT4!RpcImpersonateClient` at `0x180003038`
- `RPCRT4!RpcRevertToSelf` at `0x1800030a8`
- `RPCRT4!RpcRevertToSelf` at `0x1800030a8`

## string_xrefs

- `0x180003067`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180003086`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800030e1`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptFreeKey(void *a1, __int64 a2, __int64 a3, __int64 a4)
{
  RPC_STATUS v7; // eax
  int v8; // eax
  unsigned int v9; // ebx

  v7 = RpcImpersonateClient(a1);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        (unsigned int)"Status",
        v7,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        164);
    return 2148073504LL;
  }
  else
  {
    v8 = ((__int64 (__fastcall *)(__int64, __int64, __int64))off_180025068[0])(a2, a3, a4);
    v9 = v8;
    if ( v8 < 0 )
      DebugTraceError(
        (unsigned int)v8,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        1969);
    RpcRevertToSelf();
    return v9;
  }
}

```

## disassembly

```asm
0x180003020  mov     [rsp+arg_0], rbx
0x180003025  mov     [rsp+arg_8], rsi
0x18000302a  push    rdi
0x18000302b  sub     rsp, 50h
0x18000302f  mov     rdi, r9
0x180003032  mov     rsi, r8
0x180003035  mov     rbx, rdx
0x180003038  call    cs:__imp_RpcImpersonateClient
0x18000303e  test    eax, eax
0x180003040  jnz     short loc_1800030C0
0x180003042  mov     r8, rdi
0x180003045  mov     rdx, rsi
0x180003048  mov     rcx, rbx
0x18000304b  mov     rax, cs:off_180025068
0x180003052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003057  mov     ebx, eax
0x180003059  mov     [rsp+58h+var_18], eax
0x18000305d  test    eax, eax
0x18000305f  jns     short loc_18000307C
0x180003061  mov     r9d, 7B1h
0x180003067  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000306e  lea     rdx, aStatus; "Status"
0x180003075  mov     ecx, eax
0x180003077  call    DebugTraceError
0x18000307c  jmp     short loc_1800030A8
0x18000307e  mov     ebx, eax
0x180003080  mov     r9d, 7B7h
0x180003086  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000308d  lea     rdx, aNtstatus; "ntStatus"
0x180003094  mov     ecx, eax
0x180003096  call    DebugTraceError
0x18000309b  mov     ecx, ebx
0x18000309d  call    NormalizeNteStatus
0x1800030a2  mov     ebx, eax
0x1800030a4  mov     [rsp+58h+var_18], eax
0x1800030a8  call    cs:__imp_RpcRevertToSelf
0x1800030ae  mov     eax, ebx
0x1800030b0  mov     rbx, [rsp+58h+arg_0]
0x1800030b5  mov     rsi, [rsp+58h+arg_8]
0x1800030ba  add     rsp, 50h
0x1800030be  pop     rdi
0x1800030bf  retn
0x1800030c0  lea     rdx, WPP_GLOBAL_Control
0x1800030c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030ce  cmp     rcx, rdx
0x1800030d1  jz      short loc_180003101
0x1800030d3  test    byte ptr [rcx+1Ch], 1
0x1800030d7  jz      short loc_180003101
0x1800030d9  mov     [rsp+58h+var_28], 7A4h
0x1800030e1  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800030e8  mov     [rsp+58h+var_30], r8
0x1800030ed  mov     [rsp+58h+var_38], eax
0x1800030f1  lea     r9, aStatus; "Status"
0x1800030f8  mov     rcx, [rcx+10h]
0x1800030fc  call    WPP_SF_sDsd
0x180003101  mov     ebx, 80090020h
0x180003106  mov     eax, ebx
0x180003108  mov     rbx, [rsp+58h+arg_0]
0x18000310d  mov     rsi, [rsp+58h+arg_8]
0x180003112  add     rsp, 50h
0x180003116  pop     rdi
0x180003117  retn
```
