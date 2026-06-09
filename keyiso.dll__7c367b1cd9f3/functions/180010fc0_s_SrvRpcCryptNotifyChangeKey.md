# s_SrvRpcCryptNotifyChangeKey

- ea: `0x180010fc0`
- end: `0x180011096`
- name: `s_SrvRpcCryptNotifyChangeKey`
- size: `214`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x180010fc0`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180010fe7`
- `RPCRT4!RpcImpersonateClient` at `0x180010fe7`
- `RPCRT4!RpcRevertToSelf` at `0x18001107e`
- `RPCRT4!RpcRevertToSelf` at `0x18001107e`

## string_xrefs

- `0x180010ff7`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x18001103d`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x18001105c`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptNotifyChangeKey(void *a1, __int64 a2, __int64 a3, __int64 a4, unsigned int a5)
{
  unsigned int v8; // ebx
  unsigned int v9; // eax
  int v10; // eax

  if ( a4 )
  {
    v9 = RpcImpersonateClient(a1);
    if ( v9 )
    {
      DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 1532);
      return (unsigned int)-2146893792;
    }
    else
    {
      v10 = ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD))off_1800250C8)(a2, a3, a4, a5);
      v8 = v10;
      if ( v10 < 0 )
        DebugTraceError(
          (unsigned int)v10,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          1546);
      RpcRevertToSelf();
    }
  }
  else
  {
    return (unsigned int)-2146893785;
  }
  return v8;
}

```

## disassembly

```asm
0x180010fc0  mov     [rsp+arg_0], rbx
0x180010fc5  mov     [rsp+arg_8], rsi
0x180010fca  push    rdi
0x180010fcb  sub     rsp, 40h
0x180010fcf  mov     rbx, r9
0x180010fd2  mov     rdi, r8
0x180010fd5  mov     rsi, rdx
0x180010fd8  test    r9, r9
0x180010fdb  jnz     short loc_180010FE7
0x180010fdd  mov     ebx, 80090027h
0x180010fe2  jmp     loc_180011084
0x180010fe7  call    cs:__imp_RpcImpersonateClient
0x180010fed  test    eax, eax
0x180010fef  jz      short loc_180011013
0x180010ff1  mov     r9d, 5FCh
0x180010ff7  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010ffe  lea     rdx, aStatus; "Status"
0x180011005  mov     ecx, eax
0x180011007  call    DebugTraceError
0x18001100c  mov     ebx, 80090020h
0x180011011  jmp     short loc_180011084
0x180011013  mov     r9d, [rsp+48h+arg_20]
0x180011018  mov     r8, rbx
0x18001101b  mov     rdx, rdi
0x18001101e  mov     rcx, rsi
0x180011021  mov     rax, cs:off_1800250C8
0x180011028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001102d  mov     ebx, eax
0x18001102f  mov     [rsp+48h+var_18], eax
0x180011033  test    eax, eax
0x180011035  jns     short loc_180011052
0x180011037  mov     r9d, 60Ah
0x18001103d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011044  lea     rdx, aStatus; "Status"
0x18001104b  mov     ecx, eax
0x18001104d  call    DebugTraceError
0x180011052  jmp     short loc_18001107E
0x180011054  mov     ebx, eax
0x180011056  mov     r9d, 610h
0x18001105c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011063  lea     rdx, aNtstatus; "ntStatus"
0x18001106a  mov     ecx, eax
0x18001106c  call    DebugTraceError
0x180011071  mov     ecx, ebx
0x180011073  call    NormalizeNteStatus
0x180011078  mov     ebx, eax
0x18001107a  mov     [rsp+48h+var_18], eax
0x18001107e  call    cs:__imp_RpcRevertToSelf
0x180011084  mov     eax, ebx
0x180011086  mov     rbx, [rsp+48h+arg_0]
0x18001108b  mov     rsi, [rsp+48h+arg_8]
0x180011090  add     rsp, 40h
0x180011094  pop     rdi
0x180011095  retn
```
