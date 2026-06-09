# s_SrvRpcCryptIsAlgSupported

- ea: `0x180009090`
- end: `0x180009184`
- name: `s_SrvRpcCryptIsAlgSupported`
- size: `244`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180009090`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800090a8`
- `RPCRT4!RpcImpersonateClient` at `0x1800090a8`
- `RPCRT4!RpcRevertToSelf` at `0x180009124`
- `RPCRT4!RpcRevertToSelf` at `0x180009124`

## string_xrefs

- `0x1800090e3`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180009102`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x18000915d`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptIsAlgSupported(void *a1, __int64 a2, __int64 a3, __int64 a4, unsigned int a5)
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
        106);
    return (unsigned int)-2146893792;
  }
  else
  {
    v9 = ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD))off_180025088)(a2, a3, a4, a5);
    v10 = v9;
    if ( v9 < 0 )
      DebugTraceError(
        (unsigned int)v9,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        376);
    RpcRevertToSelf();
  }
  return v10;
}

```

## disassembly

```asm
0x180009090  mov     [rsp+arg_0], rbx
0x180009095  mov     [rsp+arg_8], rsi
0x18000909a  push    rdi
0x18000909b  sub     rsp, 50h
0x18000909f  mov     rbx, r9
0x1800090a2  mov     rdi, r8
0x1800090a5  mov     rsi, rdx
0x1800090a8  call    cs:__imp_RpcImpersonateClient
0x1800090ae  test    eax, eax
0x1800090b0  jnz     loc_18000913C
0x1800090b6  mov     r9d, [rsp+58h+arg_20]
0x1800090be  mov     r8, rbx
0x1800090c1  mov     rdx, rdi
0x1800090c4  mov     rcx, rsi
0x1800090c7  mov     rax, cs:off_180025088
0x1800090ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090d3  mov     ebx, eax
0x1800090d5  mov     [rsp+58h+var_18], eax
0x1800090d9  test    eax, eax
0x1800090db  jns     short loc_1800090F8
0x1800090dd  mov     r9d, 178h
0x1800090e3  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800090ea  lea     rdx, aStatus; "Status"
0x1800090f1  mov     ecx, eax
0x1800090f3  call    DebugTraceError
0x1800090f8  jmp     short loc_180009124
0x1800090fa  mov     ebx, eax
0x1800090fc  mov     r9d, 17Eh
0x180009102  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009109  lea     rdx, aNtstatus; "ntStatus"
0x180009110  mov     ecx, eax
0x180009112  call    DebugTraceError
0x180009117  mov     ecx, ebx
0x180009119  call    NormalizeNteStatus
0x18000911e  mov     ebx, eax
0x180009120  mov     [rsp+58h+var_18], eax
0x180009124  call    cs:__imp_RpcRevertToSelf
0x18000912a  mov     eax, ebx
0x18000912c  mov     rbx, [rsp+58h+arg_0]
0x180009131  mov     rsi, [rsp+58h+arg_8]
0x180009136  add     rsp, 50h
0x18000913a  pop     rdi
0x18000913b  retn
0x18000913c  lea     rdx, WPP_GLOBAL_Control
0x180009143  mov     rcx, cs:WPP_GLOBAL_Control
0x18000914a  cmp     rcx, rdx
0x18000914d  jz      short loc_18000917D
0x18000914f  test    byte ptr [rcx+1Ch], 1
0x180009153  jz      short loc_18000917D
0x180009155  mov     [rsp+58h+var_28], 16Ah
0x18000915d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009164  mov     [rsp+58h+var_30], r8
0x180009169  mov     [rsp+58h+var_38], eax
0x18000916d  lea     r9, aStatus; "Status"
0x180009174  mov     rcx, [rcx+10h]
0x180009178  call    WPP_SF_sDsd
0x18000917d  mov     ebx, 80090020h
0x180009182  jmp     short loc_18000912A
```
