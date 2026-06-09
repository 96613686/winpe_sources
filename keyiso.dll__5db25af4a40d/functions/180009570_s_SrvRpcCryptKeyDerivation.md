# s_SrvRpcCryptKeyDerivation

- ea: `0x180009570`
- end: `0x18000966e`
- name: `s_SrvRpcCryptKeyDerivation`
- size: `254`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, __int64, __int64, int, __int64, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x180009570`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180009588`
- `RPCRT4!RpcImpersonateClient` at `0x180009588`
- `RPCRT4!RpcRevertToSelf` at `0x180009634`
- `RPCRT4!RpcRevertToSelf` at `0x180009634`

## string_xrefs

- `0x1800095f3`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180009612`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180009652`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptKeyDerivation(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        int a9)
{
  unsigned int v12; // eax
  int v13; // eax
  unsigned int v14; // ebx

  v12 = RpcImpersonateClient(a1);
  if ( v12 )
  {
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 2003);
    return (unsigned int)-2146893792;
  }
  else
  {
    v13 = off_1800250E8(a2, a3, a4, a5, a6, a7, a8, a9);
    v14 = v13;
    if ( v13 < 0 )
      DebugTraceError(
        (unsigned int)v13,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        2021);
    RpcRevertToSelf();
  }
  return v14;
}

```

## disassembly

```asm
0x180009570  mov     [rsp+arg_0], rbx
0x180009575  mov     [rsp+arg_8], rsi
0x18000957a  push    rdi
0x18000957b  sub     rsp, 60h
0x18000957f  mov     rbx, r9
0x180009582  mov     rdi, r8
0x180009585  mov     rsi, rdx
0x180009588  call    cs:__imp_RpcImpersonateClient
0x18000958e  test    eax, eax
0x180009590  jnz     loc_18000964C
0x180009596  mov     ecx, [rsp+68h+arg_40]
0x18000959d  mov     [rsp+68h+var_30], ecx
0x1800095a1  mov     rcx, [rsp+68h+arg_38]
0x1800095a9  mov     [rsp+68h+var_38], rcx
0x1800095ae  mov     ecx, [rsp+68h+arg_30]
0x1800095b5  mov     [rsp+68h+var_40], ecx
0x1800095b9  mov     rcx, [rsp+68h+arg_28]
0x1800095c1  mov     [rsp+68h+var_48], rcx
0x1800095c6  mov     r9, [rsp+68h+arg_20]
0x1800095ce  mov     r8, rbx
0x1800095d1  mov     rdx, rdi
0x1800095d4  mov     rcx, rsi
0x1800095d7  mov     rax, cs:off_1800250E8
0x1800095de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095e3  mov     ebx, eax
0x1800095e5  mov     [rsp+68h+var_18], eax
0x1800095e9  test    eax, eax
0x1800095eb  jns     short loc_180009608
0x1800095ed  mov     r9d, 7E5h
0x1800095f3  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800095fa  lea     rdx, aStatus; "Status"
0x180009601  mov     ecx, eax
0x180009603  call    DebugTraceError
0x180009608  jmp     short loc_180009634
0x18000960a  mov     ebx, eax
0x18000960c  mov     r9d, 7EBh
0x180009612  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009619  lea     rdx, aNtstatus; "ntStatus"
0x180009620  mov     ecx, eax
0x180009622  call    DebugTraceError
0x180009627  mov     ecx, ebx
0x180009629  call    NormalizeNteStatus
0x18000962e  mov     ebx, eax
0x180009630  mov     [rsp+68h+var_18], eax
0x180009634  call    cs:__imp_RpcRevertToSelf
0x18000963a  mov     eax, ebx
0x18000963c  mov     rbx, [rsp+68h+arg_0]
0x180009641  mov     rsi, [rsp+68h+arg_8]
0x180009646  add     rsp, 60h
0x18000964a  pop     rdi
0x18000964b  retn
0x18000964c  mov     r9d, 7D3h
0x180009652  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009659  lea     rdx, aStatus; "Status"
0x180009660  mov     ecx, eax
0x180009662  call    DebugTraceError
0x180009667  mov     ebx, 80090020h
0x18000966c  jmp     short loc_18000963A
```
