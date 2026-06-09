# s_SrvRpcCryptDeleteKey

- ea: `0x180009310`
- end: `0x180009404`
- name: `s_SrvRpcCryptDeleteKey`
- size: `244`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180009310`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180009328`
- `RPCRT4!RpcImpersonateClient` at `0x180009328`
- `RPCRT4!RpcRevertToSelf` at `0x1800093a4`
- `RPCRT4!RpcRevertToSelf` at `0x1800093a4`

## string_xrefs

- `0x180009363`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180009382`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800093dd`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptDeleteKey(void *a1, __int64 a2, __int64 a3, __int64 a4, unsigned int a5)
{
  RPC_STATUS v8; // eax
  int v9; // eax
  unsigned int v10; // ebx

  v8 = RpcImpersonateClient(a1);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        (unsigned int)"Status",
        v8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        202);
    return (unsigned int)-2146893792;
  }
  else
  {
    v9 = ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD))off_180025058[0])(a2, a3, a4, a5);
    v10 = v9;
    if ( v9 < 0 )
      DebugTraceError(
        (unsigned int)v9,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        1496);
    RpcRevertToSelf();
  }
  return v10;
}

```

## disassembly

```asm
0x180009310  mov     [rsp+arg_0], rbx
0x180009315  mov     [rsp+arg_8], rsi
0x18000931a  push    rdi
0x18000931b  sub     rsp, 50h
0x18000931f  mov     rbx, r9
0x180009322  mov     rdi, r8
0x180009325  mov     rsi, rdx
0x180009328  call    cs:__imp_RpcImpersonateClient
0x18000932e  test    eax, eax
0x180009330  jnz     loc_1800093BC
0x180009336  mov     r9d, [rsp+58h+arg_20]
0x18000933e  mov     r8, rbx
0x180009341  mov     rdx, rdi
0x180009344  mov     rcx, rsi
0x180009347  mov     rax, cs:off_180025058
0x18000934e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009353  mov     ebx, eax
0x180009355  mov     [rsp+58h+var_18], eax
0x180009359  test    eax, eax
0x18000935b  jns     short loc_180009378
0x18000935d  mov     r9d, 5D8h
0x180009363  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000936a  lea     rdx, aStatus; "Status"
0x180009371  mov     ecx, eax
0x180009373  call    DebugTraceError
0x180009378  jmp     short loc_1800093A4
0x18000937a  mov     ebx, eax
0x18000937c  mov     r9d, 5DEh
0x180009382  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009389  lea     rdx, aNtstatus; "ntStatus"
0x180009390  mov     ecx, eax
0x180009392  call    DebugTraceError
0x180009397  mov     ecx, ebx
0x180009399  call    NormalizeNteStatus
0x18000939e  mov     ebx, eax
0x1800093a0  mov     [rsp+58h+var_18], eax
0x1800093a4  call    cs:__imp_RpcRevertToSelf
0x1800093aa  mov     eax, ebx
0x1800093ac  mov     rbx, [rsp+58h+arg_0]
0x1800093b1  mov     rsi, [rsp+58h+arg_8]
0x1800093b6  add     rsp, 50h
0x1800093ba  pop     rdi
0x1800093bb  retn
0x1800093bc  lea     rdx, WPP_GLOBAL_Control
0x1800093c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093ca  cmp     rcx, rdx
0x1800093cd  jz      short loc_1800093FD
0x1800093cf  test    byte ptr [rcx+1Ch], 1
0x1800093d3  jz      short loc_1800093FD
0x1800093d5  mov     [rsp+58h+var_28], 5CAh
0x1800093dd  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800093e4  mov     [rsp+58h+var_30], r8
0x1800093e9  mov     [rsp+58h+var_38], eax
0x1800093ed  lea     r9, aStatus; "Status"
0x1800093f4  mov     rcx, [rcx+10h]
0x1800093f8  call    WPP_SF_sDsd
0x1800093fd  mov     ebx, 80090020h
0x180009402  jmp     short loc_1800093AA
```
