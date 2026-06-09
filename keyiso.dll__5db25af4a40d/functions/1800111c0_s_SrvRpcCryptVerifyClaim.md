# s_SrvRpcCryptVerifyClaim

- ea: `0x1800111c0`
- end: `0x1800112d7`
- name: `s_SrvRpcCryptVerifyClaim`
- size: `279`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, __int64, int, __int64, __int64, int, __int64, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x1800111c0`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800111d8`
- `RPCRT4!RpcImpersonateClient` at `0x1800111d8`
- `RPCRT4!RpcRevertToSelf` at `0x1800112bd`
- `RPCRT4!RpcRevertToSelf` at `0x1800112bd`

## string_xrefs

- `0x1800111e8`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x18001127c`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x18001129b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptVerifyClaim(
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
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 2116);
    return (unsigned int)-2146893792;
  }
  else
  {
    v16 = off_1800250F8(a2, a3, a4, a5, a6, a7, a8, a9, a10, a11);
    v15 = v16;
    if ( v16 < 0 )
      DebugTraceError(
        (unsigned int)v16,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        2136);
    RpcRevertToSelf();
  }
  return v15;
}

```

## disassembly

```asm
0x1800111c0  mov     [rsp+arg_0], rbx
0x1800111c5  mov     [rsp+arg_8], rsi
0x1800111ca  push    rdi
0x1800111cb  sub     rsp, 70h
0x1800111cf  mov     rbx, r9
0x1800111d2  mov     rdi, r8
0x1800111d5  mov     rsi, rdx
0x1800111d8  call    cs:__imp_RpcImpersonateClient
0x1800111de  test    eax, eax
0x1800111e0  jz      short loc_180011207
0x1800111e2  mov     r9d, 844h
0x1800111e8  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800111ef  lea     rdx, aStatus; "Status"
0x1800111f6  mov     ecx, eax
0x1800111f8  call    DebugTraceError
0x1800111fd  mov     ebx, 80090020h
0x180011202  jmp     loc_1800112C3
0x180011207  mov     eax, [rsp+78h+arg_50]
0x18001120e  mov     [rsp+78h+var_30], eax
0x180011212  mov     rcx, [rsp+78h+arg_48]
0x18001121a  mov     [rsp+78h+var_38], rcx
0x18001121f  mov     ecx, [rsp+78h+arg_40]
0x180011226  mov     [rsp+78h+var_40], ecx
0x18001122a  mov     rcx, [rsp+78h+arg_38]
0x180011232  mov     [rsp+78h+var_48], rcx
0x180011237  mov     rcx, [rsp+78h+arg_30]
0x18001123f  mov     [rsp+78h+var_50], rcx
0x180011244  mov     ecx, [rsp+78h+arg_28]
0x18001124b  mov     [rsp+78h+var_58], ecx
0x18001124f  mov     r9, [rsp+78h+arg_20]
0x180011257  mov     r8, rbx
0x18001125a  mov     rdx, rdi
0x18001125d  mov     rcx, rsi
0x180011260  mov     rax, cs:off_1800250F8
0x180011267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001126c  mov     ebx, eax
0x18001126e  mov     [rsp+78h+var_18], eax
0x180011272  test    eax, eax
0x180011274  jns     short loc_180011291
0x180011276  mov     r9d, 858h
0x18001127c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011283  lea     rdx, aStatus; "Status"
0x18001128a  mov     ecx, eax
0x18001128c  call    DebugTraceError
0x180011291  jmp     short loc_1800112BD
0x180011293  mov     ebx, eax
0x180011295  mov     r9d, 85Eh
0x18001129b  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800112a2  lea     rdx, aNtstatus; "ntStatus"
0x1800112a9  mov     ecx, eax
0x1800112ab  call    DebugTraceError
0x1800112b0  mov     ecx, ebx
0x1800112b2  call    NormalizeNteStatus
0x1800112b7  mov     ebx, eax
0x1800112b9  mov     [rsp+78h+var_18], eax
0x1800112bd  call    cs:__imp_RpcRevertToSelf
0x1800112c3  mov     eax, ebx
0x1800112c5  lea     r11, [rsp+78h+var_8]
0x1800112ca  mov     rbx, [r11+10h]
0x1800112ce  mov     rsi, [r11+18h]
0x1800112d2  mov     rsp, r11
0x1800112d5  pop     rdi
0x1800112d6  retn
```
