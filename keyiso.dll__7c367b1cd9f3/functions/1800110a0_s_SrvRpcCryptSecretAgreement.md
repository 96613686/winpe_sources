# s_SrvRpcCryptSecretAgreement

- ea: `0x1800110a0`
- end: `0x1800111ae`
- name: `s_SrvRpcCryptSecretAgreement`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x1800110a0`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800110e8`
- `RPCRT4!RpcImpersonateClient` at `0x1800110e8`
- `RPCRT4!RpcRevertToSelf` at `0x18001119c`
- `RPCRT4!RpcRevertToSelf` at `0x18001119c`

## string_xrefs

- `0x1800110cb`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800110f8`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x18001115b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x18001117a`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptSecretAgreement(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        int a7)
{
  unsigned int v10; // ebx
  unsigned int v11; // eax
  int v12; // eax

  if ( a6 )
  {
    v11 = RpcImpersonateClient(a1);
    if ( v11 )
    {
      DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 1585);
      return (unsigned int)-2146893792;
    }
    else
    {
      *a6 = -1;
      v12 = off_1800250D0(a2, a3, a4, a5, (__int64)a6, a7);
      v10 = v12;
      if ( v12 < 0 )
        DebugTraceError(
          (unsigned int)v12,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          1603);
      RpcRevertToSelf();
    }
  }
  else
  {
    v10 = -2146893785;
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 1578);
  }
  return v10;
}

```

## disassembly

```asm
0x1800110a0  push    rbx
0x1800110a2  push    rsi
0x1800110a3  push    rdi
0x1800110a4  push    r14
0x1800110a6  sub     rsp, 58h
0x1800110aa  mov     rdi, r9
0x1800110ad  mov     rsi, r8
0x1800110b0  mov     r14, rdx
0x1800110b3  mov     rbx, [rsp+78h+arg_28]
0x1800110bb  test    rbx, rbx
0x1800110be  jnz     short loc_1800110E8
0x1800110c0  mov     ebx, 80090027h
0x1800110c5  mov     r9d, 62Ah
0x1800110cb  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800110d2  lea     rdx, aStatus; "Status"
0x1800110d9  mov     ecx, 80090027h
0x1800110de  call    DebugTraceError
0x1800110e3  jmp     loc_1800111A2
0x1800110e8  call    cs:__imp_RpcImpersonateClient
0x1800110ee  test    eax, eax
0x1800110f0  jz      short loc_180011117
0x1800110f2  mov     r9d, 631h
0x1800110f8  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800110ff  lea     rdx, aStatus; "Status"
0x180011106  mov     ecx, eax
0x180011108  call    DebugTraceError
0x18001110d  mov     ebx, 80090020h
0x180011112  jmp     loc_1800111A2
0x180011117  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18001111e  mov     eax, [rsp+78h+arg_30]
0x180011125  mov     [rsp+78h+var_50], eax
0x180011129  mov     [rsp+78h+var_58], rbx
0x18001112e  mov     r9, [rsp+78h+arg_20]
0x180011136  mov     r8, rdi
0x180011139  mov     rdx, rsi
0x18001113c  mov     rcx, r14
0x18001113f  mov     rax, cs:off_1800250D0
0x180011146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001114b  mov     ebx, eax
0x18001114d  mov     [rsp+78h+var_38], eax
0x180011151  test    eax, eax
0x180011153  jns     short loc_180011170
0x180011155  mov     r9d, 643h
0x18001115b  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011162  lea     rdx, aStatus; "Status"
0x180011169  mov     ecx, eax
0x18001116b  call    DebugTraceError
0x180011170  jmp     short loc_18001119C
0x180011172  mov     ebx, eax
0x180011174  mov     r9d, 649h
0x18001117a  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011181  lea     rdx, aNtstatus; "ntStatus"
0x180011188  mov     ecx, eax
0x18001118a  call    DebugTraceError
0x18001118f  mov     ecx, ebx
0x180011191  call    NormalizeNteStatus
0x180011196  mov     ebx, eax
0x180011198  mov     [rsp+78h+var_38], eax
0x18001119c  call    cs:__imp_RpcRevertToSelf
0x1800111a2  mov     eax, ebx
0x1800111a4  add     rsp, 58h
0x1800111a8  pop     r14
0x1800111aa  pop     rdi
0x1800111ab  pop     rsi
0x1800111ac  pop     rbx
0x1800111ad  retn
```
