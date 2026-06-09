# s_SrvRpcCryptOpenKey

- ea: `0x180003120`
- end: `0x180003269`
- name: `s_SrvRpcCryptOpenKey`
- size: `329`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003120`
- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180003141`
- `RPCRT4!RpcImpersonateClient` at `0x180003141`
- `RPCRT4!RpcRevertToSelf` at `0x180003202`
- `RPCRT4!RpcRevertToSelf` at `0x180003202`

## string_xrefs

- `0x1800031b6`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800031e0`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180003242`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptOpenKey(void *a1, __int64 a2, __int64 a3, _QWORD *a4, __int64 a5, int a6, int a7)
{
  RPC_STATUS v10; // edx
  int v11; // r8d
  int v12; // edx
  int v13; // ebx
  int v14; // r8d

  if ( a4 )
  {
    v10 = RpcImpersonateClient(a1);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v10,
          v11,
          (unsigned int)"Status",
          v10,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          158);
      return (unsigned int)-2146893792;
    }
    else
    {
      *a4 = -1;
      v13 = off_180025020(a2, a3, (int)a4, a5, a6, a7);
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
          176);
      }
      RpcRevertToSelf();
    }
  }
  else
  {
    return (unsigned int)-2146893785;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180003120  mov     [rsp+arg_0], rbx
0x180003125  mov     [rsp+arg_8], rsi
0x18000312a  push    rdi
0x18000312b  sub     rsp, 50h
0x18000312f  mov     rbx, r9
0x180003132  mov     rdi, r8
0x180003135  mov     rsi, rdx
0x180003138  test    r9, r9
0x18000313b  jz      loc_18000321A
0x180003141  call    cs:__imp_RpcImpersonateClient
0x180003147  mov     edx, eax
0x180003149  test    eax, eax
0x18000314b  jnz     loc_180003221
0x180003151  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180003158  mov     eax, [rsp+58h+arg_30]
0x18000315f  mov     dword ptr [rsp+58h+var_30], eax
0x180003163  mov     eax, [rsp+58h+arg_28]
0x18000316a  mov     [rsp+58h+var_38], eax
0x18000316e  mov     r9, [rsp+58h+arg_20]
0x180003176  mov     r8, rbx
0x180003179  mov     rdx, rdi
0x18000317c  mov     rcx, rsi
0x18000317f  mov     rax, cs:off_180025020
0x180003186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000318b  mov     ebx, eax
0x18000318d  mov     [rsp+58h+var_18], eax
0x180003191  test    eax, eax
0x180003193  jns     short loc_1800031D6
0x180003195  lea     rax, WPP_GLOBAL_Control
0x18000319c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031a3  cmp     rcx, rax
0x1800031a6  jz      short loc_1800031D6
0x1800031a8  test    byte ptr [rcx+1Ch], 1
0x1800031ac  jz      short loc_1800031D6
0x1800031ae  mov     [rsp+58h+var_28], 1B0h
0x1800031b6  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800031bd  mov     [rsp+58h+var_30], rax
0x1800031c2  mov     [rsp+58h+var_38], ebx
0x1800031c6  lea     r9, aStatus; "Status"
0x1800031cd  mov     rcx, [rcx+10h]
0x1800031d1  call    WPP_SF_sDsd
0x1800031d6  jmp     short loc_180003202
0x1800031d8  mov     ebx, eax
0x1800031da  mov     r9d, 1B6h
0x1800031e0  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800031e7  lea     rdx, aNtstatus; "ntStatus"
0x1800031ee  mov     ecx, eax
0x1800031f0  call    DebugTraceError
0x1800031f5  mov     ecx, ebx
0x1800031f7  call    NormalizeNteStatus
0x1800031fc  mov     ebx, eax
0x1800031fe  mov     [rsp+58h+var_18], eax
0x180003202  call    cs:__imp_RpcRevertToSelf
0x180003208  mov     eax, ebx
0x18000320a  mov     rbx, [rsp+58h+arg_0]
0x18000320f  mov     rsi, [rsp+58h+arg_8]
0x180003214  add     rsp, 50h
0x180003218  pop     rdi
0x180003219  retn
0x18000321a  mov     ebx, 80090027h
0x18000321f  jmp     short loc_180003208
0x180003221  lea     rax, WPP_GLOBAL_Control
0x180003228  mov     rcx, cs:WPP_GLOBAL_Control
0x18000322f  cmp     rcx, rax
0x180003232  jz      short loc_180003262
0x180003234  test    byte ptr [rcx+1Ch], 1
0x180003238  jz      short loc_180003262
0x18000323a  mov     [rsp+58h+var_28], 19Eh
0x180003242  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003249  mov     [rsp+58h+var_30], rax
0x18000324e  mov     [rsp+58h+var_38], edx
0x180003252  lea     r9, aStatus; "Status"
0x180003259  mov     rcx, [rcx+10h]
0x18000325d  call    WPP_SF_sDsd
0x180003262  mov     ebx, 80090020h
0x180003267  jmp     short loc_180003208
```
