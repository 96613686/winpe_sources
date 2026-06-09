# s_SrvRpcCryptCreateClaim

- ea: `0x180010810`
- end: `0x180010927`
- name: `s_SrvRpcCryptCreateClaim`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x180010810`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180010828`
- `RPCRT4!RpcImpersonateClient` at `0x180010828`
- `RPCRT4!RpcRevertToSelf` at `0x18001090d`
- `RPCRT4!RpcRevertToSelf` at `0x18001090d`

## string_xrefs

- `0x180010838`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800108cc`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800108eb`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptCreateClaim(
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
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 2058);
    return (unsigned int)-2146893792;
  }
  else
  {
    v16 = off_1800250F0[0](a2, a3, a4, a5, a6, a7, a8, a9, a10, a11);
    v15 = v16;
    if ( v16 < 0 )
      DebugTraceError(
        (unsigned int)v16,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        2078);
    RpcRevertToSelf();
  }
  return v15;
}

```

## disassembly

```asm
0x180010810  mov     [rsp+arg_0], rbx
0x180010815  mov     [rsp+arg_8], rsi
0x18001081a  push    rdi
0x18001081b  sub     rsp, 70h
0x18001081f  mov     rbx, r9
0x180010822  mov     rdi, r8
0x180010825  mov     rsi, rdx
0x180010828  call    cs:__imp_RpcImpersonateClient
0x18001082e  test    eax, eax
0x180010830  jz      short loc_180010857
0x180010832  mov     r9d, 80Ah
0x180010838  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001083f  lea     rdx, aStatus; "Status"
0x180010846  mov     ecx, eax
0x180010848  call    DebugTraceError
0x18001084d  mov     ebx, 80090020h
0x180010852  jmp     loc_180010913
0x180010857  mov     eax, [rsp+78h+arg_50]
0x18001085e  mov     [rsp+78h+var_30], eax
0x180010862  mov     rcx, [rsp+78h+arg_48]
0x18001086a  mov     [rsp+78h+var_38], rcx
0x18001086f  mov     ecx, [rsp+78h+arg_40]
0x180010876  mov     [rsp+78h+var_40], ecx
0x18001087a  mov     rcx, [rsp+78h+arg_38]
0x180010882  mov     [rsp+78h+var_48], rcx
0x180010887  mov     rcx, [rsp+78h+arg_30]
0x18001088f  mov     [rsp+78h+var_50], rcx
0x180010894  mov     ecx, [rsp+78h+arg_28]
0x18001089b  mov     [rsp+78h+var_58], ecx
0x18001089f  mov     r9, [rsp+78h+arg_20]
0x1800108a7  mov     r8, rbx
0x1800108aa  mov     rdx, rdi
0x1800108ad  mov     rcx, rsi
0x1800108b0  mov     rax, cs:off_1800250F0
0x1800108b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108bc  mov     ebx, eax
0x1800108be  mov     [rsp+78h+var_18], eax
0x1800108c2  test    eax, eax
0x1800108c4  jns     short loc_1800108E1
0x1800108c6  mov     r9d, 81Eh
0x1800108cc  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800108d3  lea     rdx, aStatus; "Status"
0x1800108da  mov     ecx, eax
0x1800108dc  call    DebugTraceError
0x1800108e1  jmp     short loc_18001090D
0x1800108e3  mov     ebx, eax
0x1800108e5  mov     r9d, 824h
0x1800108eb  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800108f2  lea     rdx, aNtstatus; "ntStatus"
0x1800108f9  mov     ecx, eax
0x1800108fb  call    DebugTraceError
0x180010900  mov     ecx, ebx
0x180010902  call    NormalizeNteStatus
0x180010907  mov     ebx, eax
0x180010909  mov     [rsp+78h+var_18], eax
0x18001090d  call    cs:__imp_RpcRevertToSelf
0x180010913  mov     eax, ebx
0x180010915  lea     r11, [rsp+78h+var_8]
0x18001091a  mov     rbx, [r11+10h]
0x18001091e  mov     rsi, [r11+18h]
0x180010922  mov     rsp, r11
0x180010925  pop     rdi
0x180010926  retn
```
