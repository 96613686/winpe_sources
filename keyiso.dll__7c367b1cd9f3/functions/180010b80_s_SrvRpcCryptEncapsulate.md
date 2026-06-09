# s_SrvRpcCryptEncapsulate

- ea: `0x180010b80`
- end: `0x180010c97`
- name: `s_SrvRpcCryptEncapsulate`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x180010b80`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180010b98`
- `RPCRT4!RpcImpersonateClient` at `0x180010b98`
- `RPCRT4!RpcRevertToSelf` at `0x180010c7d`
- `RPCRT4!RpcRevertToSelf` at `0x180010c7d`

## string_xrefs

- `0x180010ba8`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180010c3c`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180010c5b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptEncapsulate(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        __int64 a10,
        int a11)
{
  unsigned int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax

  v14 = RpcImpersonateClient(a1);
  if ( v14 )
  {
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 2173);
    return (unsigned int)-2146893792;
  }
  else
  {
    v16 = off_180025110(a2, a3, a4, a5, a6, a7, a8, a9, a10, a11);
    v15 = v16;
    if ( v16 < 0 )
      DebugTraceError(
        (unsigned int)v16,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        2193);
    RpcRevertToSelf();
  }
  return v15;
}

```

## disassembly

```asm
0x180010b80  mov     [rsp+arg_0], rbx
0x180010b85  mov     [rsp+arg_8], rsi
0x180010b8a  push    rdi
0x180010b8b  sub     rsp, 70h
0x180010b8f  mov     rbx, r9
0x180010b92  mov     rdi, r8
0x180010b95  mov     rsi, rdx
0x180010b98  call    cs:__imp_RpcImpersonateClient
0x180010b9e  test    eax, eax
0x180010ba0  jz      short loc_180010BC7
0x180010ba2  mov     r9d, 87Dh
0x180010ba8  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010baf  lea     rdx, aStatus; "Status"
0x180010bb6  mov     ecx, eax
0x180010bb8  call    DebugTraceError
0x180010bbd  mov     ebx, 80090020h
0x180010bc2  jmp     loc_180010C83
0x180010bc7  mov     eax, [rsp+78h+arg_50]
0x180010bce  mov     [rsp+78h+var_30], eax
0x180010bd2  mov     rcx, [rsp+78h+arg_48]
0x180010bda  mov     [rsp+78h+var_38], rcx
0x180010bdf  mov     ecx, [rsp+78h+arg_40]
0x180010be6  mov     [rsp+78h+var_40], ecx
0x180010bea  mov     rcx, [rsp+78h+arg_38]
0x180010bf2  mov     [rsp+78h+var_48], rcx
0x180010bf7  mov     rcx, [rsp+78h+arg_30]
0x180010bff  mov     [rsp+78h+var_50], rcx
0x180010c04  mov     ecx, [rsp+78h+arg_28]
0x180010c0b  mov     [rsp+78h+var_58], ecx
0x180010c0f  mov     r9, [rsp+78h+arg_20]
0x180010c17  mov     r8, rbx
0x180010c1a  mov     rdx, rdi
0x180010c1d  mov     rcx, rsi
0x180010c20  mov     rax, cs:off_180025110
0x180010c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c2c  mov     ebx, eax
0x180010c2e  mov     [rsp+78h+var_18], eax
0x180010c32  test    eax, eax
0x180010c34  jns     short loc_180010C51
0x180010c36  mov     r9d, 891h
0x180010c3c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010c43  lea     rdx, aStatus; "Status"
0x180010c4a  mov     ecx, eax
0x180010c4c  call    DebugTraceError
0x180010c51  jmp     short loc_180010C7D
0x180010c53  mov     ebx, eax
0x180010c55  mov     r9d, 897h
0x180010c5b  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010c62  lea     rdx, aNtstatus; "ntStatus"
0x180010c69  mov     ecx, eax
0x180010c6b  call    DebugTraceError
0x180010c70  mov     ecx, ebx
0x180010c72  call    NormalizeNteStatus
0x180010c77  mov     ebx, eax
0x180010c79  mov     [rsp+78h+var_18], eax
0x180010c7d  call    cs:__imp_RpcRevertToSelf
0x180010c83  mov     eax, ebx
0x180010c85  lea     r11, [rsp+78h+var_8]
0x180010c8a  mov     rbx, [r11+10h]
0x180010c8e  mov     rsi, [r11+18h]
0x180010c92  mov     rsp, r11
0x180010c95  pop     rdi
0x180010c96  retn
```
