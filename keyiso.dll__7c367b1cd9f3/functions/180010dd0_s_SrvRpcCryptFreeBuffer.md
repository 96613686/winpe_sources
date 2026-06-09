# s_SrvRpcCryptFreeBuffer

- ea: `0x180010dd0`
- end: `0x180010eaf`
- name: `s_SrvRpcCryptFreeBuffer`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x180010dd0`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180010e0d`
- `RPCRT4!RpcImpersonateClient` at `0x180010e0d`
- `RPCRT4!RpcRevertToSelf` at `0x180010e9c`
- `RPCRT4!RpcRevertToSelf` at `0x180010e9c`

## string_xrefs

- `0x180010df0`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180010e1d`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180010e5b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180010e7a`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptFreeBuffer(void *a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // ebx
  unsigned int v6; // eax
  int v7; // eax

  if ( a3 )
  {
    v6 = RpcImpersonateClient(a1);
    if ( v6 )
    {
      DebugTraceError(v6, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 1875);
      return (unsigned int)-2146893792;
    }
    else
    {
      v7 = ((__int64 (__fastcall *)(__int64, __int64))off_180025070)(a2, a3);
      v5 = v7;
      if ( v7 < 0 )
        DebugTraceError(
          (unsigned int)v7,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          1887);
      RpcRevertToSelf();
    }
  }
  else
  {
    v5 = -2146893785;
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 1868);
  }
  return v5;
}

```

## disassembly

```asm
0x180010dd0  mov     [rsp+arg_0], rbx
0x180010dd5  push    rdi
0x180010dd6  sub     rsp, 30h
0x180010dda  mov     rbx, r8
0x180010ddd  mov     rdi, rdx
0x180010de0  test    r8, r8
0x180010de3  jnz     short loc_180010E0D
0x180010de5  mov     ebx, 80090027h
0x180010dea  mov     r9d, 74Ch
0x180010df0  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010df7  lea     rdx, aStatus; "Status"
0x180010dfe  mov     ecx, 80090027h
0x180010e03  call    DebugTraceError
0x180010e08  jmp     loc_180010EA2
0x180010e0d  call    cs:__imp_RpcImpersonateClient
0x180010e13  test    eax, eax
0x180010e15  jz      short loc_180010E39
0x180010e17  mov     r9d, 753h
0x180010e1d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010e24  lea     rdx, aStatus; "Status"
0x180010e2b  mov     ecx, eax
0x180010e2d  call    DebugTraceError
0x180010e32  mov     ebx, 80090020h
0x180010e37  jmp     short loc_180010EA2
0x180010e39  mov     rdx, rbx
0x180010e3c  mov     rcx, rdi
0x180010e3f  mov     rax, cs:off_180025070
0x180010e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e4b  mov     ebx, eax
0x180010e4d  mov     [rsp+38h+var_18], eax
0x180010e51  test    eax, eax
0x180010e53  jns     short loc_180010E70
0x180010e55  mov     r9d, 75Fh
0x180010e5b  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010e62  lea     rdx, aStatus; "Status"
0x180010e69  mov     ecx, eax
0x180010e6b  call    DebugTraceError
0x180010e70  jmp     short loc_180010E9C
0x180010e72  mov     ebx, eax
0x180010e74  mov     r9d, 765h
0x180010e7a  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010e81  lea     rdx, aNtstatus; "ntStatus"
0x180010e88  mov     ecx, eax
0x180010e8a  call    DebugTraceError
0x180010e8f  mov     ecx, ebx
0x180010e91  call    NormalizeNteStatus
0x180010e96  mov     ebx, eax
0x180010e98  mov     [rsp+38h+var_18], eax
0x180010e9c  call    cs:__imp_RpcRevertToSelf
0x180010ea2  mov     eax, ebx
0x180010ea4  mov     rbx, [rsp+38h+arg_0]
0x180010ea9  add     rsp, 30h
0x180010ead  pop     rdi
0x180010eae  retn
```
