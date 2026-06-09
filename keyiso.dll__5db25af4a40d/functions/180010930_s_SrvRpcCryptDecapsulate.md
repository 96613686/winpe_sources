# s_SrvRpcCryptDecapsulate

- ea: `0x180010930`
- end: `0x180010a38`
- name: `s_SrvRpcCryptDecapsulate`
- size: `264`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, __int64, int, __int64, int, __int64, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x180010930`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180010948`
- `RPCRT4!RpcImpersonateClient` at `0x180010948`
- `RPCRT4!RpcRevertToSelf` at `0x180010a20`
- `RPCRT4!RpcRevertToSelf` at `0x180010a20`

## string_xrefs

- `0x180010958`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800109df`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800109fe`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptDecapsulate(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        int a8,
        __int64 a9,
        int a10)
{
  unsigned int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax

  v13 = RpcImpersonateClient(a1);
  if ( v13 )
  {
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 2229);
    return (unsigned int)-2146893792;
  }
  else
  {
    v15 = off_180025118(a2, a3, a4, a5, a6, a7, a8, a9, a10);
    v14 = v15;
    if ( v15 < 0 )
      DebugTraceError(
        (unsigned int)v15,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        2248);
    RpcRevertToSelf();
  }
  return v14;
}

```

## disassembly

```asm
0x180010930  mov     [rsp+arg_0], rbx
0x180010935  mov     [rsp+arg_8], rsi
0x18001093a  push    rdi
0x18001093b  sub     rsp, 60h
0x18001093f  mov     rbx, r9
0x180010942  mov     rdi, r8
0x180010945  mov     rsi, rdx
0x180010948  call    cs:__imp_RpcImpersonateClient
0x18001094e  test    eax, eax
0x180010950  jz      short loc_180010977
0x180010952  mov     r9d, 8B5h
0x180010958  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001095f  lea     rdx, aStatus; "Status"
0x180010966  mov     ecx, eax
0x180010968  call    DebugTraceError
0x18001096d  mov     ebx, 80090020h
0x180010972  jmp     loc_180010A26
0x180010977  mov     ecx, [rsp+68h+arg_48]
0x18001097e  mov     [rsp+68h+var_28], ecx
0x180010982  mov     rcx, [rsp+68h+arg_40]
0x18001098a  mov     [rsp+68h+var_30], rcx
0x18001098f  mov     ecx, [rsp+68h+arg_38]
0x180010996  mov     [rsp+68h+var_38], ecx
0x18001099a  mov     rcx, [rsp+68h+arg_30]
0x1800109a2  mov     [rsp+68h+var_40], rcx
0x1800109a7  mov     ecx, [rsp+68h+arg_28]
0x1800109ae  mov     [rsp+68h+var_48], ecx
0x1800109b2  mov     r9, [rsp+68h+arg_20]
0x1800109ba  mov     r8, rbx
0x1800109bd  mov     rdx, rdi
0x1800109c0  mov     rcx, rsi
0x1800109c3  mov     rax, cs:off_180025118
0x1800109ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109cf  mov     ebx, eax
0x1800109d1  mov     [rsp+68h+var_18], eax
0x1800109d5  test    eax, eax
0x1800109d7  jns     short loc_1800109F4
0x1800109d9  mov     r9d, 8C8h
0x1800109df  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800109e6  lea     rdx, aStatus; "Status"
0x1800109ed  mov     ecx, eax
0x1800109ef  call    DebugTraceError
0x1800109f4  jmp     short loc_180010A20
0x1800109f6  mov     ebx, eax
0x1800109f8  mov     r9d, 8CEh
0x1800109fe  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010a05  lea     rdx, aNtstatus; "ntStatus"
0x180010a0c  mov     ecx, eax
0x180010a0e  call    DebugTraceError
0x180010a13  mov     ecx, ebx
0x180010a15  call    NormalizeNteStatus
0x180010a1a  mov     ebx, eax
0x180010a1c  mov     [rsp+68h+var_18], eax
0x180010a20  call    cs:__imp_RpcRevertToSelf
0x180010a26  mov     eax, ebx
0x180010a28  mov     rbx, [rsp+68h+arg_0]
0x180010a2d  mov     rsi, [rsp+68h+arg_8]
0x180010a32  add     rsp, 60h
0x180010a36  pop     rdi
0x180010a37  retn
```
