# s_SrvRpcCryptCipherEncrypt

- ea: `0x180010660`
- end: `0x180010802`
- name: `s_SrvRpcCryptCipherEncrypt`
- size: `418`
- prototype: `__int64 __usercall@<rax>(RPC_BINDING_HANDLE BindingHandle@<rcx>, __int64, int, __int64, __int64, int, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x18000d0ac`
- `0x180010398`
- `0x180010660`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180010709`
- `RPCRT4!RpcImpersonateClient` at `0x180010709`
- `RPCRT4!RpcRevertToSelf` at `0x1800107e9`
- `RPCRT4!RpcRevertToSelf` at `0x1800107e9`

## string_xrefs

- `0x1800106cb`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180010719`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800107a8`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800107c7`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptCipherEncrypt(
        RPC_BINDING_HANDLE BindingHandle,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        _DWORD *a10,
        int a11)
{
  unsigned int v15; // ebx
  __int64 v16; // r9
  __int64 v17; // rcx
  int v18; // eax
  unsigned int v19; // eax
  int v20; // eax
  _OWORD v22[2]; // [rsp+68h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+88h] [rbp-A0h]
  _BYTE v24[152]; // [rsp+90h] [rbp-98h] BYREF

  memset(v22, 0, sizeof(v22));
  v23 = 0;
  memset_0(v24, 0, 0x58u);
  if ( !a10 )
  {
    v15 = -2146893785;
    v16 = 1006;
    v17 = 2148073511LL;
LABEL_3:
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", v16);
    return v15;
  }
  v18 = UnpackCipherPaddingInfo(a7, v22, v24);
  v15 = v18;
  if ( v18 < 0 )
  {
    v16 = 1020;
    v17 = (unsigned int)v18;
    goto LABEL_3;
  }
  v19 = RpcImpersonateClient(BindingHandle);
  if ( v19 )
  {
    DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 1029);
    return (unsigned int)-2146893792;
  }
  else
  {
    *a10 = 0;
    v20 = off_180025078[0](a2, a3, a4, a5, a6, (__int64)v22, a8, a9, (__int64)a10, a11);
    v15 = v20;
    if ( v20 < 0 )
      DebugTraceError(
        (unsigned int)v20,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        1051);
    RpcRevertToSelf();
  }
  return v15;
}

```

## disassembly

```asm
0x180010660  push    rbx
0x180010662  push    rsi
0x180010663  push    rdi
0x180010664  push    r12
0x180010666  push    r14
0x180010668  push    r15
0x18001066a  sub     rsp, 0F8h
0x180010671  mov     r14, r9
0x180010674  mov     r15, r8
0x180010677  mov     r12, rdx
0x18001067a  mov     rdi, rcx
0x18001067d  xorps   xmm0, xmm0
0x180010680  xor     eax, eax
0x180010682  movups  [rsp+128h+var_C0], xmm0
0x180010687  movups  [rsp+128h+var_B0], xmm0
0x18001068c  mov     [rsp+128h+var_A0], rax
0x180010694  xor     edx, edx; Val
0x180010696  lea     r8d, [rax+58h]; Size
0x18001069a  lea     rcx, [rsp+128h+var_98]; void *
0x1800106a2  call    memset_0
0x1800106a7  mov     rsi, [rsp+128h+arg_48]
0x1800106af  test    rsi, rsi
0x1800106b2  jnz     short loc_1800106DC
0x1800106b4  mov     ebx, 80090027h
0x1800106b9  mov     r9d, 3EEh
0x1800106bf  mov     ecx, 80090027h
0x1800106c4  lea     rdx, aStatus; "Status"
0x1800106cb  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800106d2  call    DebugTraceError
0x1800106d7  jmp     loc_1800107EF
0x1800106dc  lea     r8, [rsp+128h+var_98]
0x1800106e4  lea     rdx, [rsp+128h+var_C0]
0x1800106e9  mov     rcx, [rsp+128h+arg_30]
0x1800106f1  call    _UnpackCipherPaddingInfo
0x1800106f6  mov     ebx, eax
0x1800106f8  test    eax, eax
0x1800106fa  jns     short loc_180010706
0x1800106fc  mov     r9d, 3FCh
0x180010702  mov     ecx, eax
0x180010704  jmp     short loc_1800106C4
0x180010706  mov     rcx, rdi; BindingHandle
0x180010709  call    cs:__imp_RpcImpersonateClient
0x18001070f  test    eax, eax
0x180010711  jz      short loc_180010738
0x180010713  mov     r9d, 405h
0x180010719  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010720  lea     rdx, aStatus; "Status"
0x180010727  mov     ecx, eax
0x180010729  call    DebugTraceError
0x18001072e  mov     ebx, 80090020h
0x180010733  jmp     loc_1800107EF
0x180010738  mov     dword ptr [rsi], 0
0x18001073e  mov     ecx, [rsp+128h+arg_50]
0x180010745  mov     [rsp+128h+var_E0], ecx
0x180010749  mov     [rsp+128h+var_E8], rsi
0x18001074e  mov     ecx, [rsp+128h+arg_40]
0x180010755  mov     [rsp+128h+var_F0], ecx
0x180010759  mov     rcx, [rsp+128h+arg_38]
0x180010761  mov     [rsp+128h+var_F8], rcx
0x180010766  lea     rax, [rsp+128h+var_C0]
0x18001076b  mov     [rsp+128h+var_100], rax
0x180010770  mov     ecx, [rsp+128h+arg_28]
0x180010777  mov     [rsp+128h+var_108], ecx
0x18001077b  mov     r9, [rsp+128h+arg_20]
0x180010783  mov     r8, r14
0x180010786  mov     rdx, r15
0x180010789  mov     rcx, r12
0x18001078c  mov     rax, cs:off_180025078
0x180010793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010798  mov     ebx, eax
0x18001079a  mov     [rsp+128h+var_C8], eax
0x18001079e  test    eax, eax
0x1800107a0  jns     short loc_1800107BD
0x1800107a2  mov     r9d, 41Bh
0x1800107a8  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800107af  lea     rdx, aStatus; "Status"
0x1800107b6  mov     ecx, eax
0x1800107b8  call    DebugTraceError
0x1800107bd  jmp     short loc_1800107E9
0x1800107bf  mov     ebx, eax
0x1800107c1  mov     r9d, 421h
0x1800107c7  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800107ce  lea     rdx, aNtstatus; "ntStatus"
0x1800107d5  mov     ecx, eax
0x1800107d7  call    DebugTraceError
0x1800107dc  mov     ecx, ebx
0x1800107de  call    NormalizeNteStatus
0x1800107e3  mov     ebx, eax
0x1800107e5  mov     [rsp+128h+var_C8], eax
0x1800107e9  call    cs:__imp_RpcRevertToSelf
0x1800107ef  mov     eax, ebx
0x1800107f1  add     rsp, 0F8h
0x1800107f8  pop     r15
0x1800107fa  pop     r14
0x1800107fc  pop     r12
0x1800107fe  pop     rdi
0x1800107ff  pop     rsi
0x180010800  pop     rbx
0x180010801  retn
```
