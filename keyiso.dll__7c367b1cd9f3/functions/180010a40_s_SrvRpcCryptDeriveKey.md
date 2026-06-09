# s_SrvRpcCryptDeriveKey

- ea: `0x180010a40`
- end: `0x180010b72`
- name: `s_SrvRpcCryptDeriveKey`
- size: `306`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x180010a40`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180010a88`
- `RPCRT4!RpcImpersonateClient` at `0x180010a88`
- `RPCRT4!RpcRevertToSelf` at `0x180010b60`
- `RPCRT4!RpcRevertToSelf` at `0x180010b60`

## string_xrefs

- `0x180010a6b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180010a98`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180010b1f`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180010b3e`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptDeriveKey(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int a8,
        _DWORD *a9,
        int a10)
{
  unsigned int v13; // ebx
  unsigned int v14; // eax
  int v15; // eax

  if ( a9 )
  {
    v14 = RpcImpersonateClient(a1);
    if ( v14 )
    {
      DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 1645);
      return (unsigned int)-2146893792;
    }
    else
    {
      *a9 = 0;
      v15 = off_1800250D8(a2, a3, a4, a5, a6, a7, a8, (__int64)a9, a10);
      v13 = v15;
      if ( v15 < 0 )
        DebugTraceError(
          (unsigned int)v15,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          1666);
      RpcRevertToSelf();
    }
  }
  else
  {
    v13 = -2146893785;
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 1638);
  }
  return v13;
}

```

## disassembly

```asm
0x180010a40  push    rbx
0x180010a42  push    rsi
0x180010a43  push    rdi
0x180010a44  push    r14
0x180010a46  sub     rsp, 68h
0x180010a4a  mov     rdi, r9
0x180010a4d  mov     rsi, r8
0x180010a50  mov     r14, rdx
0x180010a53  mov     rbx, [rsp+88h+arg_40]
0x180010a5b  test    rbx, rbx
0x180010a5e  jnz     short loc_180010A88
0x180010a60  mov     ebx, 80090027h
0x180010a65  mov     r9d, 666h
0x180010a6b  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010a72  lea     rdx, aStatus; "Status"
0x180010a79  mov     ecx, 80090027h
0x180010a7e  call    DebugTraceError
0x180010a83  jmp     loc_180010B66
0x180010a88  call    cs:__imp_RpcImpersonateClient
0x180010a8e  test    eax, eax
0x180010a90  jz      short loc_180010AB7
0x180010a92  mov     r9d, 66Dh
0x180010a98  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010a9f  lea     rdx, aStatus; "Status"
0x180010aa6  mov     ecx, eax
0x180010aa8  call    DebugTraceError
0x180010aad  mov     ebx, 80090020h
0x180010ab2  jmp     loc_180010B66
0x180010ab7  mov     dword ptr [rbx], 0
0x180010abd  mov     eax, [rsp+88h+arg_48]
0x180010ac4  mov     [rsp+88h+var_48], eax
0x180010ac8  mov     [rsp+88h+var_50], rbx
0x180010acd  mov     eax, [rsp+88h+arg_38]
0x180010ad4  mov     [rsp+88h+var_58], eax
0x180010ad8  mov     rax, [rsp+88h+arg_30]
0x180010ae0  mov     [rsp+88h+var_60], rax
0x180010ae5  mov     rax, [rsp+88h+arg_28]
0x180010aed  mov     [rsp+88h+var_68], rax
0x180010af2  mov     r9, [rsp+88h+arg_20]
0x180010afa  mov     r8, rdi
0x180010afd  mov     rdx, rsi
0x180010b00  mov     rcx, r14
0x180010b03  mov     rax, cs:off_1800250D8
0x180010b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b0f  mov     ebx, eax
0x180010b11  mov     [rsp+88h+var_38], eax
0x180010b15  test    eax, eax
0x180010b17  jns     short loc_180010B34
0x180010b19  mov     r9d, 682h
0x180010b1f  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010b26  lea     rdx, aStatus; "Status"
0x180010b2d  mov     ecx, eax
0x180010b2f  call    DebugTraceError
0x180010b34  jmp     short loc_180010B60
0x180010b36  mov     ebx, eax
0x180010b38  mov     r9d, 688h
0x180010b3e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010b45  lea     rdx, aNtstatus; "ntStatus"
0x180010b4c  mov     ecx, eax
0x180010b4e  call    DebugTraceError
0x180010b53  mov     ecx, ebx
0x180010b55  call    NormalizeNteStatus
0x180010b5a  mov     ebx, eax
0x180010b5c  mov     [rsp+88h+var_38], eax
0x180010b60  call    cs:__imp_RpcRevertToSelf
0x180010b66  mov     eax, ebx
0x180010b68  add     rsp, 68h
0x180010b6c  pop     r14
0x180010b6e  pop     rdi
0x180010b6f  pop     rsi
0x180010b70  pop     rbx
0x180010b71  retn
```
