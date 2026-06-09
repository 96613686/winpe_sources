# s_SrvRpcCryptFreeSecret

- ea: `0x180010ec0`
- end: `0x180010faf`
- name: `s_SrvRpcCryptFreeSecret`
- size: `239`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x180010ec0`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180010f05`
- `RPCRT4!RpcImpersonateClient` at `0x180010f05`
- `RPCRT4!RpcRevertToSelf` at `0x180010f97`
- `RPCRT4!RpcRevertToSelf` at `0x180010f97`

## string_xrefs

- `0x180010ee8`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180010f15`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180010f56`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180010f75`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptFreeSecret(void *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v7; // ebx
  unsigned int v8; // eax
  int v9; // eax

  if ( a4 )
  {
    v8 = RpcImpersonateClient(a1);
    if ( v8 )
    {
      DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 1702);
      return (unsigned int)-2146893792;
    }
    else
    {
      v9 = ((__int64 (__fastcall *)(__int64, __int64, __int64))off_1800250E0)(a2, a3, a4);
      v7 = v9;
      if ( v9 < 0 )
        DebugTraceError(
          (unsigned int)v9,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          1715);
      RpcRevertToSelf();
    }
  }
  else
  {
    v7 = -2146893785;
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 1695);
  }
  return v7;
}

```

## disassembly

```asm
0x180010ec0  mov     [rsp+arg_0], rbx
0x180010ec5  mov     [rsp+arg_8], rsi
0x180010eca  push    rdi
0x180010ecb  sub     rsp, 30h
0x180010ecf  mov     rbx, r9
0x180010ed2  mov     rdi, r8
0x180010ed5  mov     rsi, rdx
0x180010ed8  test    r9, r9
0x180010edb  jnz     short loc_180010F05
0x180010edd  mov     ebx, 80090027h
0x180010ee2  mov     r9d, 69Fh
0x180010ee8  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010eef  lea     rdx, aStatus; "Status"
0x180010ef6  mov     ecx, 80090027h
0x180010efb  call    DebugTraceError
0x180010f00  jmp     loc_180010F9D
0x180010f05  call    cs:__imp_RpcImpersonateClient
0x180010f0b  test    eax, eax
0x180010f0d  jz      short loc_180010F31
0x180010f0f  mov     r9d, 6A6h
0x180010f15  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010f1c  lea     rdx, aStatus; "Status"
0x180010f23  mov     ecx, eax
0x180010f25  call    DebugTraceError
0x180010f2a  mov     ebx, 80090020h
0x180010f2f  jmp     short loc_180010F9D
0x180010f31  mov     r8, rbx
0x180010f34  mov     rdx, rdi
0x180010f37  mov     rcx, rsi
0x180010f3a  mov     rax, cs:off_1800250E0
0x180010f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f46  mov     ebx, eax
0x180010f48  mov     [rsp+38h+var_18], eax
0x180010f4c  test    eax, eax
0x180010f4e  jns     short loc_180010F6B
0x180010f50  mov     r9d, 6B3h
0x180010f56  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010f5d  lea     rdx, aStatus; "Status"
0x180010f64  mov     ecx, eax
0x180010f66  call    DebugTraceError
0x180010f6b  jmp     short loc_180010F97
0x180010f6d  mov     ebx, eax
0x180010f6f  mov     r9d, 6B9h
0x180010f75  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010f7c  lea     rdx, aNtstatus; "ntStatus"
0x180010f83  mov     ecx, eax
0x180010f85  call    DebugTraceError
0x180010f8a  mov     ecx, ebx
0x180010f8c  call    NormalizeNteStatus
0x180010f91  mov     ebx, eax
0x180010f93  mov     [rsp+38h+var_18], eax
0x180010f97  call    cs:__imp_RpcRevertToSelf
0x180010f9d  mov     eax, ebx
0x180010f9f  mov     rbx, [rsp+38h+arg_0]
0x180010fa4  mov     rsi, [rsp+38h+arg_8]
0x180010fa9  add     rsp, 30h
0x180010fad  pop     rdi
0x180010fae  retn
```
