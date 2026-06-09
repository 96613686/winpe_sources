# s_SrvRpcCryptEnumKeys

- ea: `0x180010ca0`
- end: `0x180010dbc`
- name: `s_SrvRpcCryptEnumKeys`
- size: `284`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x180010ca0`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180010cfc`
- `RPCRT4!RpcImpersonateClient` at `0x180010cfc`
- `RPCRT4!RpcRevertToSelf` at `0x180010da9`
- `RPCRT4!RpcRevertToSelf` at `0x180010da9`

## string_xrefs

- `0x180010cca`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180010d0c`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180010d68`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180010d87`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptEnumKeys(void *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6, int a7)
{
  __int64 v10; // r9
  unsigned int v11; // ebx
  unsigned int v12; // eax
  int v13; // eax

  if ( !a5 )
  {
    v10 = 1810;
LABEL_3:
    v11 = -2146893785;
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", v10);
    return v11;
  }
  if ( !a6 )
  {
    v10 = 1817;
    goto LABEL_3;
  }
  v12 = RpcImpersonateClient(a1);
  if ( v12 )
  {
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 1824);
    return (unsigned int)-2146893792;
  }
  else
  {
    v13 = off_180025098(a2, a3, a4, a5, a6, a7);
    v11 = v13;
    if ( v13 < 0 )
      DebugTraceError(
        (unsigned int)v13,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        1840);
    RpcRevertToSelf();
  }
  return v11;
}

```

## disassembly

```asm
0x180010ca0  push    rbx
0x180010ca2  push    rsi
0x180010ca3  push    r14
0x180010ca5  push    r15
0x180010ca7  sub     rsp, 58h
0x180010cab  mov     rsi, r9
0x180010cae  mov     r14, r8
0x180010cb1  mov     r15, rdx
0x180010cb4  cmp     [rsp+78h+arg_20], 0
0x180010cbd  jnz     short loc_180010CE7
0x180010cbf  mov     r9d, 712h
0x180010cc5  mov     ebx, 80090027h
0x180010cca  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010cd1  lea     rdx, aStatus; "Status"
0x180010cd8  mov     ecx, 80090027h
0x180010cdd  call    DebugTraceError
0x180010ce2  jmp     loc_180010DAF
0x180010ce7  mov     rbx, [rsp+78h+arg_28]
0x180010cef  test    rbx, rbx
0x180010cf2  jnz     short loc_180010CFC
0x180010cf4  mov     r9d, 719h
0x180010cfa  jmp     short loc_180010CC5
0x180010cfc  call    cs:__imp_RpcImpersonateClient
0x180010d02  test    eax, eax
0x180010d04  jz      short loc_180010D2B
0x180010d06  mov     r9d, 720h
0x180010d0c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010d13  lea     rdx, aStatus; "Status"
0x180010d1a  mov     ecx, eax
0x180010d1c  call    DebugTraceError
0x180010d21  mov     ebx, 80090020h
0x180010d26  jmp     loc_180010DAF
0x180010d2b  mov     eax, [rsp+78h+arg_30]
0x180010d32  mov     [rsp+78h+var_50], eax
0x180010d36  mov     [rsp+78h+var_58], rbx
0x180010d3b  mov     r9, [rsp+78h+arg_20]
0x180010d43  mov     r8, rsi
0x180010d46  mov     rdx, r14
0x180010d49  mov     rcx, r15
0x180010d4c  mov     rax, cs:off_180025098
0x180010d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d58  mov     ebx, eax
0x180010d5a  mov     [rsp+78h+var_38], eax
0x180010d5e  test    eax, eax
0x180010d60  jns     short loc_180010D7D
0x180010d62  mov     r9d, 730h
0x180010d68  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010d6f  lea     rdx, aStatus; "Status"
0x180010d76  mov     ecx, eax
0x180010d78  call    DebugTraceError
0x180010d7d  jmp     short loc_180010DA9
0x180010d7f  mov     ebx, eax
0x180010d81  mov     r9d, 736h
0x180010d87  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010d8e  lea     rdx, aNtstatus; "ntStatus"
0x180010d95  mov     ecx, eax
0x180010d97  call    DebugTraceError
0x180010d9c  mov     ecx, ebx
0x180010d9e  call    NormalizeNteStatus
0x180010da3  mov     ebx, eax
0x180010da5  mov     [rsp+78h+var_38], eax
0x180010da9  call    cs:__imp_RpcRevertToSelf
0x180010daf  mov     eax, ebx
0x180010db1  add     rsp, 58h
0x180010db5  pop     r15
0x180010db7  pop     r14
0x180010db9  pop     rsi
0x180010dba  pop     rbx
0x180010dbb  retn
```
