# s_SrvRpcCryptOpenStorageProvider

- ea: `0x180006d60`
- end: `0x180006e52`
- name: `s_SrvRpcCryptOpenStorageProvider`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x180006d60`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180006d81`
- `RPCRT4!RpcImpersonateClient` at `0x180006d81`
- `RPCRT4!RpcRevertToSelf` at `0x180006e01`
- `RPCRT4!RpcRevertToSelf` at `0x180006e01`

## string_xrefs

- `0x180006dc0`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180006ddf`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180006e36`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptOpenStorageProvider(void *a1, __int64 a2, _QWORD *a3, __int64 a4, unsigned int a5)
{
  unsigned int v8; // eax
  int v9; // eax
  unsigned int v10; // ebx

  if ( !a3 )
    return 2148073511LL;
  v8 = RpcImpersonateClient(a1);
  if ( v8 )
  {
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 316);
    return (unsigned int)-2146893792;
  }
  else
  {
    *a3 = -1;
    v9 = ((__int64 (__fastcall *)(__int64, _QWORD *, __int64, _QWORD))off_180025018)(a2, a3, a4, a5);
    v10 = v9;
    if ( v9 < 0 )
      DebugTraceError(
        (unsigned int)v9,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        332);
    RpcRevertToSelf();
  }
  return v10;
}

```

## disassembly

```asm
0x180006d60  mov     [rsp+arg_0], rbx
0x180006d65  mov     [rsp+arg_8], rsi
0x180006d6a  push    rdi
0x180006d6b  sub     rsp, 40h
0x180006d6f  mov     rdi, r9
0x180006d72  mov     rbx, r8
0x180006d75  mov     rsi, rdx
0x180006d78  test    r8, r8
0x180006d7b  jz      loc_180006E19
0x180006d81  call    cs:__imp_RpcImpersonateClient
0x180006d87  test    eax, eax
0x180006d89  jnz     loc_180006E30
0x180006d8f  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180006d96  mov     r9d, [rsp+48h+arg_20]
0x180006d9b  mov     r8, rdi
0x180006d9e  mov     rdx, rbx
0x180006da1  mov     rcx, rsi
0x180006da4  mov     rax, cs:off_180025018
0x180006dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006db0  mov     ebx, eax
0x180006db2  mov     [rsp+48h+var_18], eax
0x180006db6  test    eax, eax
0x180006db8  jns     short loc_180006DD5
0x180006dba  mov     r9d, 14Ch
0x180006dc0  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006dc7  lea     rdx, aStatus; "Status"
0x180006dce  mov     ecx, eax
0x180006dd0  call    DebugTraceError
0x180006dd5  jmp     short loc_180006E01
0x180006dd7  mov     ebx, eax
0x180006dd9  mov     r9d, 152h
0x180006ddf  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006de6  lea     rdx, aNtstatus; "ntStatus"
0x180006ded  mov     ecx, eax
0x180006def  call    DebugTraceError
0x180006df4  mov     ecx, ebx
0x180006df6  call    NormalizeNteStatus
0x180006dfb  mov     ebx, eax
0x180006dfd  mov     [rsp+48h+var_18], eax
0x180006e01  call    cs:__imp_RpcRevertToSelf
0x180006e07  mov     eax, ebx
0x180006e09  mov     rbx, [rsp+48h+arg_0]
0x180006e0e  mov     rsi, [rsp+48h+arg_8]
0x180006e13  add     rsp, 40h
0x180006e17  pop     rdi
0x180006e18  retn
0x180006e19  mov     ebx, 80090027h
0x180006e1e  mov     eax, ebx
0x180006e20  mov     rbx, [rsp+48h+arg_0]
0x180006e25  mov     rsi, [rsp+48h+arg_8]
0x180006e2a  add     rsp, 40h
0x180006e2e  pop     rdi
0x180006e2f  retn
0x180006e30  mov     r9d, 13Ch
0x180006e36  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006e3d  lea     rdx, aStatus; "Status"
0x180006e44  mov     ecx, eax
0x180006e46  call    DebugTraceError
0x180006e4b  mov     ebx, 80090020h
0x180006e50  jmp     short loc_180006E07
```
