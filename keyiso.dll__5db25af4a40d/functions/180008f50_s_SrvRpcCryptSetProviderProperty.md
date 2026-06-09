# s_SrvRpcCryptSetProviderProperty

- ea: `0x180008f50`
- end: `0x180009080`
- name: `s_SrvRpcCryptSetProviderProperty`
- size: `304`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, __int64, int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180008f50`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180008f68`
- `RPCRT4!RpcImpersonateClient` at `0x180008f68`
- `RPCRT4!RpcRevertToSelf` at `0x180009020`
- `RPCRT4!RpcRevertToSelf` at `0x180009020`

## string_xrefs

- `0x180008fd4`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180008ffe`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180009059`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptSetProviderProperty(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7)
{
  RPC_STATUS v10; // eax
  int v11; // r8d
  int v12; // edx
  int v13; // ebx
  int v14; // r8d

  v10 = RpcImpersonateClient(a1);
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)WPP_GLOBAL_Control,
        v11,
        (unsigned int)"Status",
        v10,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        70);
    return (unsigned int)-2146893792;
  }
  else
  {
    v13 = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64, int, int))off_180025040)(a2, a3, a4, a5, a6, a7);
    if ( v13 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        v14,
        (unsigned int)"Status",
        v13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        86);
    }
    RpcRevertToSelf();
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180008f50  mov     [rsp+arg_0], rbx
0x180008f55  mov     [rsp+arg_8], rsi
0x180008f5a  push    rdi
0x180008f5b  sub     rsp, 50h
0x180008f5f  mov     rbx, r9
0x180008f62  mov     rdi, r8
0x180008f65  mov     rsi, rdx
0x180008f68  call    cs:__imp_RpcImpersonateClient
0x180008f6e  test    eax, eax
0x180008f70  jnz     loc_180009038
0x180008f76  mov     ecx, [rsp+58h+arg_30]
0x180008f7d  mov     dword ptr [rsp+58h+var_30], ecx
0x180008f81  mov     ecx, [rsp+58h+arg_28]
0x180008f88  mov     [rsp+58h+var_38], ecx
0x180008f8c  mov     r9, [rsp+58h+arg_20]
0x180008f94  mov     r8, rbx
0x180008f97  mov     rdx, rdi
0x180008f9a  mov     rcx, rsi
0x180008f9d  mov     rax, cs:off_180025040
0x180008fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fa9  mov     ebx, eax
0x180008fab  mov     [rsp+58h+var_18], eax
0x180008faf  test    eax, eax
0x180008fb1  jns     short loc_180008FF4
0x180008fb3  lea     rcx, WPP_GLOBAL_Control
0x180008fba  mov     rax, cs:WPP_GLOBAL_Control
0x180008fc1  cmp     rax, rcx
0x180008fc4  jz      short loc_180008FF4
0x180008fc6  test    byte ptr [rax+1Ch], 1
0x180008fca  jz      short loc_180008FF4
0x180008fcc  mov     [rsp+58h+var_28], 256h
0x180008fd4  lea     rcx, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008fdb  mov     [rsp+58h+var_30], rcx
0x180008fe0  mov     [rsp+58h+var_38], ebx
0x180008fe4  lea     r9, aStatus; "Status"
0x180008feb  mov     rcx, [rax+10h]
0x180008fef  call    WPP_SF_sDsd
0x180008ff4  jmp     short loc_180009020
0x180008ff6  mov     ebx, eax
0x180008ff8  mov     r9d, 25Ch
0x180008ffe  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009005  lea     rdx, aNtstatus; "ntStatus"
0x18000900c  mov     ecx, eax
0x18000900e  call    DebugTraceError
0x180009013  mov     ecx, ebx
0x180009015  call    NormalizeNteStatus
0x18000901a  mov     ebx, eax
0x18000901c  mov     [rsp+58h+var_18], eax
0x180009020  call    cs:__imp_RpcRevertToSelf
0x180009026  mov     eax, ebx
0x180009028  mov     rbx, [rsp+58h+arg_0]
0x18000902d  mov     rsi, [rsp+58h+arg_8]
0x180009032  add     rsp, 50h
0x180009036  pop     rdi
0x180009037  retn
0x180009038  lea     rcx, WPP_GLOBAL_Control
0x18000903f  mov     rdx, cs:WPP_GLOBAL_Control
0x180009046  cmp     rdx, rcx
0x180009049  jz      short loc_180009079
0x18000904b  test    byte ptr [rdx+1Ch], 1
0x18000904f  jz      short loc_180009079
0x180009051  mov     [rsp+58h+var_28], 246h
0x180009059  lea     rcx, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009060  mov     [rsp+58h+var_30], rcx
0x180009065  mov     [rsp+58h+var_38], eax
0x180009069  lea     r9, aStatus; "Status"
0x180009070  mov     rcx, [rdx+10h]
0x180009074  call    WPP_SF_sDsd
0x180009079  mov     ebx, 80090020h
0x18000907e  jmp     short loc_180009026
```
